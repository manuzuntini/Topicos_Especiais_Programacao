# Aula 7 - Chatbots com base de conhecimento - Dify (26/09/2024)

---

Na aula 7, instalamos e configuramos o **Dify** para criar chatbots com uma base de conhecimento personalizada, utilizando a plataforma para organizar e automatizar interações de atendimento.

### Instalação do Dify

1. **Clonagem do Repositório**: Clonamos o repositório do Dify:
    
    ```bash
    git clone <https://github.com/langgenius/dify.git>
    cd dify/docker
    
    ```
    
2. **Configuração do Arquivo `.env`**: Criamos uma cópia do arquivo `.env`, configuramos a porta do NGINX e definimos uma senha inicial para o usuário admin:
    
    ```bash
    cp .env.example .env
    EXPOSE_NGINX_PORT=8080
    INIT_PASSWORD=sk-9f73s3ljTX
    
    ```
    
3. **Executando com Docker**: Iniciamos o Docker Compose para subir o serviço:
    
    ```bash
    docker compose up -d
    
    ```
    
4. **Atualizações**: Aprendemos a atualizar o Dify com `git pull` e Docker Compose:
    
    ```bash
    cd dify/docker
    docker compose down
    git pull origin main
    docker compose pull
    docker compose up -d
    
    ```
    

### Introdução ao Dify

Após a instalação, exploramos o Dify e suas funcionalidades como uma plataforma para desenvolver chatbots que utilizam uma base de conhecimento. Discutimos como o Dify facilita a configuração de chatbots e a utilização de uma interface para organizar e acessar informações de maneira automatizada.