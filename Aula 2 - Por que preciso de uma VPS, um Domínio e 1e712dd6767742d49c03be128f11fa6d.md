# Aula 2 - Por que preciso de uma VPS, um Domínio e DNS (Cloudflare (22/08/2024)

Nesta aula, aprendemos sobre várias ferramentas e tecnologias fundamentais para o desenvolvimento moderno, incluindo **VPS**, **Domínio**, **DNS (Cloudflare)**, e plataformas como **Docker** e **WSL 2**. Também exploramos mecanismos de busca como **DuckDuckGo** e integramos essas tecnologias em nosso ambiente de desenvolvimento.

### **O que é uma VPS e para que serve?**

- **VPS (Virtual Private Server)** é um servidor virtual privado que oferece controle completo sobre os recursos e o ambiente do servidor. Diferentemente da hospedagem compartilhada, uma VPS isola seus recursos, oferecendo desempenho superior e maior personalização para hospedar aplicações web.
- **Para que serve uma VPS?**
    - **Hospedagem de sites e aplicações**: Ideal para hospedar sites, sistemas, bancos de dados e outras aplicações que precisam de controle total sobre o ambiente de execução.
    - **Ambientes de desenvolvimento**: Uma VPS pode ser usada para configurar ambientes de desenvolvimento e teste, simulando o ambiente de produção.
    - **Serviços de cloud**: VPS também é utilizada para serviços como servidores de e-mail, backup e até servidores de jogos.
- **Benefícios de usar uma VPS**:
    - **Escalabilidade**: Ajuste de recursos conforme as necessidades da aplicação aumentam.
    - **Controle total**: Capacidade de instalar qualquer software ou modificar o sistema.
    - **Desempenho e segurança**: Maior segurança e desempenho, já que os recursos são dedicados à sua aplicação.

---

### **Domínio e DNS (Cloudflare)**

- **Domínio**: O domínio é o nome que identifica um site na web. Ele facilita o acesso ao conteúdo hospedado na VPS, permitindo que os usuários acessem a aplicação com um nome amigável, como `www.meusite.com`, em vez de um endereço IP.
- **Para que serve um domínio?**
    - **Identificação única**: Facilita a lembrança e o acesso ao site.
    - **Profissionalismo**: Domínios próprios conferem uma imagem mais profissional para seu projeto.
- **DNS (Domain Name System)**: O DNS é o sistema que traduz o domínio em um endereço IP. O **Cloudflare** é um dos serviços de DNS mais utilizados por sua capacidade de melhorar a segurança e o desempenho de sites.
- **Benefícios do Cloudflare**:
    - **Segurança**: Proteção contra ataques DDoS.
    - **Desempenho**: Cache distribuído globalmente, melhorando a velocidade de acesso.
    - **Facilidade de gerenciamento**: A interface do Cloudflare permite uma configuração rápida e visual das entradas DNS.

---

**Ferramentas de busca e automação com Python e DuckDuckGo**

- **DuckDuckGo**: Discutimos o uso do DuckDuckGo, um mecanismo de busca que prioriza a privacidade dos usuários. Diferentemente de outros mecanismos de busca, o DuckDuckGo não rastreia o histórico de pesquisa dos usuários, garantindo uma navegação anônima.
- **Integração com Python**: Instalamos a biblioteca Langchain no Python, que permite realizar pesquisas automatizadas com DuckDuckGo. Também testamos o código que permite realizar pesquisas diretamente pelo Python, integrando a automação de busca de dados.
- **Exemplo prático**: Durante a aula, fizemos uma pesquisa sobre a cantora Taylor Swift, onde encontramos uma notícia sobre o cancelamento de shows devido a um ataque terrorista. A pesquisa foi realizada com o DuckDuckGo via script Python.
- **Expansão de funcionalidades**: Exploramos o uso de outras ferramentas, como a Wikipedia e o YouTube, que podem ser integradas via bibliotecas Python para complementar as funcionalidades de busca e trazer diferentes fontes de informação para nossas aplicações.

---

### **Docker e WSL 2: O que são e por que utilizá-los?**

- **Docker** é uma plataforma que permite "containerizar" aplicações, empacotando-as com todas as suas dependências para que possam ser executadas de maneira idêntica em qualquer ambiente. Durante a aula, aprendemos a usar o Docker para facilitar o desenvolvimento e deploy de aplicações.
- **Benefícios do Docker**:
    - **Consistência**: A aplicação roda da mesma maneira em qualquer ambiente.
    - **Portabilidade**: Um container Docker pode ser movido para qualquer máquina que tenha Docker instalado.
- **WSL 2 (Windows Subsystem for Linux)**:
    - O **WSL 2** permite rodar um ambiente Linux dentro do Windows, oferecendo um kernel Linux real que melhora o desempenho e a compatibilidade com ferramentas baseadas em Unix, como o Docker.
    - Com o Docker integrado ao WSL 2, conseguimos rodar containers Linux diretamente no Windows de forma eficiente.

---

**Uso do Docker com WSL 2 no Windows**

- **Docker Desktop com WSL 2**:
    - Utilizamos o Docker Desktop integrado ao WSL 2, que roda sobre a **Virtual Machine Platform**, eliminando a necessidade de uma licença PRO do Windows. O Docker Desktop facilita o gerenciamento visual de containers, a instalação de extensões e o uso de clusters Kubernetes locais.
- **Vantagens do Docker com WSL 2**:
    - **Melhor desempenho**: O Docker roda com mais eficiência no ambiente WSL 2 do que no Windows nativo.
    - **Interface visual**: O Docker Desktop oferece uma interface gráfica para administrar containers e extensões.
    - **Facilidade de uso**: A integração com o WSL 2 permite rodar ambientes baseados em Unix sem precisar de uma máquina virtual separada.
- **Desvantagens**:
    - O Docker Desktop pode consumir bastante memória, mesmo quando não está rodando containers. Em alguns casos, é necessário reiniciar o Docker para resolver problemas de funcionamento.

---

### **Instalação do Ubuntu e Ferramentas de LLMs**

- Instalamos o **Ubuntu** no WSL 2 como parte da configuração de nosso ambiente de desenvolvimento. Isso permitiu criar um ambiente Linux completo dentro do Windows, facilitando o uso de ferramentas que exigem sistemas baseados em Unix.
- **Ferramentas de LLMs (Large Language Models)**:
    - Baixamos e configuramos ferramentas essenciais para trabalhar com **Large Language Models**, como o **LLM Studio**, **Anything LLM**, e **Ollama**. Essas ferramentas são importantes para o desenvolvimento de soluções baseadas em IA e aprendizado de máquina.