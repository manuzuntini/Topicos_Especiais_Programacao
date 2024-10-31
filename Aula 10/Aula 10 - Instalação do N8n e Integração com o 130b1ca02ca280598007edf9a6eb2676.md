# Aula 10 - Instalação do N8n e Integração com o Whatsapp (24/10/24)

---

Na aula 10, trabalhamos na instalação e configuração de APIs para automação de mensagens no WhatsApp usando **N8n** e o serviço **go-whatsapp-web-multidevice**. O objetivo foi implementar o envio de mensagens automáticas via API HTTP, facilitando a comunicação com os clientes.

### Instalação e Configuração do go-whatsapp-web-multidevice

1. **Configuração com Docker Compose**: Configuramos o serviço de envio de mensagens no WhatsApp com `go-whatsapp-web-multidevice`, permitindo o envio de mensagens via API HTTP.
    - Exemplo de `docker-compose.yaml` para configurar o serviço:
        
        ```yaml
        version: '3.9'
        services:
          whatsapp_go:
            image: "aldinokemal2104/go-whatsapp-web-multidevice:latest"
            ports:
              - "3100:3000"
            environment:
              - WEBHOOK="<https://n8n.semcodigo.edu.pl/webhook-test/consultavendas>"
            volumes:
              - whatsapp_data:/app/storages
        volumes:
          whatsapp_data:
        
        ```
        
2. **Execução com Docker CLI**: Outra forma de rodar o serviço diretamente com o Docker CLI, configurando webhook e resposta automática:
    
    ```bash
    sudo docker run --detach --publish=3001:3000 --name=whatsapp2 --restart=always --volume=$(sudo docker volume create --name=whatsapp2):/app/storages aldinokemal2104/go-whatsapp-web-multidevice --autoreply="Don't reply this message please" --webhook="<http://localhost:5678/webhook-test/whats>"
    
    ```
    

### Desafios e Problemas com Agendamentos

Durante a aula, enfrentamos desafios técnicos relacionados ao agendamento de interações e à configuração de webhooks para o WhatsApp. Esses problemas nos levaram a revisar os parâmetros e as integrações com o N8n, buscando identificar as causas e trabalhar em soluções que pudessem estabilizar o fluxo de mensagens e agendamentos futuros.

### Aplicação Prática

Apesar dos problemas enfrentados, a aula trouxe uma compreensão prática dos passos de instalação e configuração de APIs de WhatsApp, permitindo que o serviço estivesse funcional para uso básico de envio de mensagens. Continuaremos trabalhando nas configurações de agendamentos e automatizações para melhorar a estabilidade e a eficiência do sistema.