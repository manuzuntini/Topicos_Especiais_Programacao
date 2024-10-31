# Aula 8 - Chatbots com base de conhecimento - Dify (03/10/2024 - 03/10/2024)

---

Na aula 8, continuamos o conteúdo da aula anterior, expandindo as funcionalidades do **Dify** com a introdução do **N8n** para criação de fluxos de automação personalizados. A integração do N8n permite que chatbots, configurados no Dify, possam realizar tarefas automáticas, ampliando a capacidade de resposta e processamento de dados.

### Instalação do N8n

1. **Configuração Inicial**: Criamos uma pasta para o N8n:
    
    ```bash
    mkdir n8n
    cd n8n/
    
    ```
    
2. **Arquivo `docker-compose.yaml`**: Configuramos o arquivo `docker-compose.yaml` para iniciar o N8n com autenticação básica, garantindo a segurança de acesso:
    
    ```yaml
    version: "3.2"
    services:
      n8n:
        image: n8nio/n8n
        ports:
          - "5678:5678"
        environment:
          - N8N_BASIC_AUTH_USER=admin
          - N8N_BASIC_AUTH_PASSWORD=8H4a10032024
        volumes:
          - n8n_data:/home/node/.n8n
        networks:
          - n8n-net
    
    volumes:
      n8n_data:
    
    networks:
      n8n-net:
        name: n8n-net
        driver: bridge
    
    ```
    

---

**Criação de Fluxo de Atendimento**

Na aula 8, implementamos um fluxo de atendimento automatizado para uma concessionária, usando uma estrutura baseada em JSON Schema para guiar o agente nas interações com o usuário e garantir respostas formatadas e consistentes. O fluxo foi dividido em duas partes, utilizando prompts específicos para cada etapa de atendimento, representados pelos personagens "Clara" e "Caetano."

### Formato de Resposta com JSON Schema

Definimos o formato de resposta do modelo em JSON Schema, contendo os seguintes campos:

- **nome**: Nome do usuário.
- **carro**: Carro escolhido pelo usuário (ou uma string vazia se não especificado).
- **response**: A resposta do agente para o usuário.
- **etapa**: Número da etapa em que o agente está, conforme descrito nas tags de <etapas>.

Esse formato assegura que todas as respostas sigam uma estrutura padrão, facilitando o processamento das informações nas próximas etapas do atendimento.

### Fluxo do Atendimento - Prompt LLM 1 (Agente Clara)

O agente "Clara" foi configurado para orientar o cliente na escolha do carro ideal:

1. **Início da Conversa**: Clara envia a logo da loja em formato markdown.
2. **Coleta de Informações**: Pergunta o nome do usuário e identifica o tipo de uso do carro.
3. **Sugestão de Carros**: Com base nas respostas, Clara sugere um ou mais modelos que atendam às necessidades do cliente.
4. **Encaminhamento para o Gerente**: Após a escolha do carro, Clara agradece e encaminha o cliente para o gerente "Caetano" para agendar o test drive.

### Agendamento do Test Drive - Prompt LLM 2 (Agente Caetano)

O agente "Caetano" foi configurado para agendar o test drive:

1. **Confirmação de Endereço**: Solicita o endereço do usuário.
2. **Sugestão de Datas e Horários**: Oferece duas opções de datas, uma de manhã e outra à tarde, com base na data atual e no dia da semana, que são calculados automaticamente.
3. **Confirmação Final**: Após escolher o horário, Caetano agradece e confirma o agendamento com o cliente.

### Código para Obter a Data Atual

Para facilitar a sugestão de datas e dias da semana, utilizamos um código Python para obter a data atual e o dia da semana em português:

```python
from datetime import datetime
def main() -> dict:
    days_of_week = {
        0: "Segunda-feira",
        1: "Terça-feira",
        2: "Quarta-feira",
        3: "Quinta-feira",
        4: "Sexta-feira",
        5: "Sábado",
        6: "Domingo"
    }
    current_date = datetime.now()
    formatted_date = current_date.strftime("%d/%m/%Y")
    day_of_week = days_of_week[current_date.weekday()]

    return {
        "data_atual": formatted_date,
        "dia_da_semana": day_of_week
    }

```

Esse código fornece informações precisas para os agentes "Clara" e "Caetano", que usam a data e o dia da semana para sugerir horários de forma dinâmica.