# Aula 9 - Implementação de chatbot/Agent no Dify (10/09/24)

---

Na aula 9, avançamos no uso do Dify, focando na implementação de um chatbot para a **Clínica Médica Saúde Total** com integração à API do [Cal.com](http://cal.com/). Esse chatbot foi configurado para auxiliar no agendamento de consultas e fornecer informações sobre os serviços médicos da clínica.

### Configuração do Chatbot/Agent no Dify

O chatbot foi configurado com um contexto específico da clínica, destacando os serviços e tratamentos oferecidos, como reabilitação muscular e articular, terapias preventivas e fisioterapia ortopédica. Além disso, definimos um tom de comunicação **calmo e acolhedor**, com um nível de formalidade adequado ao ambiente médico.

### Etapas do Agendamento Automatizado

1. **Coleta de Dados do Paciente**: O agente solicita o nome, e-mail e telefone do paciente.
2. **Seleção de Data e Hora**: Pergunta ao paciente a data desejada e, com base nos slots disponíveis, sugere horários usando a API `get_slots_cal_com`.
3. **Confirmação do Agendamento**: Após o paciente selecionar o horário, o agente utiliza a função `criar_agendamento_cal_com` para finalizar o agendamento e confirmar a reserva com a ferramenta `get_bookings_cal_com`.
4. **Ajustes de Horário e Fuso Horário**: Para garantir precisão, o chatbot considera o fuso horário GMT -4 para informar corretamente as horas e dias da semana, ajustando a hora fornecida pela ferramenta `current_time`, que opera em GMT 0.