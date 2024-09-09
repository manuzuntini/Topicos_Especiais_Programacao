# Aula 3 - Engenharia de Prompt (29/08/2024)

Na **Aula 4**, exploramos profundamente a **Engenharia de Prompt (EP)**, uma disciplina emergente focada na criação e otimização de **prompts** — instruções textuais que orientam os modelos de linguagem de grande escala (LLMs) a gerar respostas precisas e úteis. Esse processo é essencial para maximizar a eficiência dos LLMs, já que os prompts determinam como os modelos interpretam e processam as solicitações dos usuários.

A criação dos prompts é um processo interativo que envolve planejamento, testes e refinamentos constantes. A clareza, neutralidade e imparcialidade são fundamentais para a eficácia dos prompts. A escolha cuidadosa das palavras pode influenciar diretamente as respostas dos modelos, evitando interpretações tendenciosas ou imprecisas. Além disso, aprendemos que a **Engenharia de Prompt** também envolve a personalização e reestruturação de prompts para diferentes públicos e aplicações, a fim de garantir que os resultados sejam adequados ao contexto específico.

### Técnicas Básicas de Engenharia de Prompt

Durante a aula, discutimos algumas técnicas importantes para melhorar o desempenho dos LLMs por meio da criação e otimização dos prompts:

1. **Temperatura**:
    - A temperatura controla a aleatoriedade nas respostas do modelo. Valores baixos de temperatura resultam em respostas mais determinísticas e concisas, enquanto valores mais altos tornam as respostas mais criativas e diversificadas.
2. **Tokens**:
    - Os tokens representam a unidade de processamento dos modelos, sendo que aproximadamente 4 caracteres equivalem a um token. O controle do número de tokens é importante para limitar ou expandir a quantidade de informação que o modelo pode processar e gerar.
3. **TopP**:
    - O **TopP** é utilizado para controlar a probabilidade acumulada de seleção de respostas. Manter um valor baixo para TopP faz com que o modelo forneça respostas mais precisas e confiáveis.

### Aplicação Prática: Exemplo com Billie Eilish

Um dos exemplos práticos que exploramos durante a aula foi a formulação de diferentes prompts para gerar informações sobre a cantora **Billie Eilish**. Ao usar uma temperatura baixa, o modelo forneceu uma resposta direta e objetiva, como "Billie Eilish é uma cantora e compositora americana famosa por sua música inovadora e seu estilo único." Essa resposta focou nas informações essenciais e factuais sobre a artista.

No entanto, quando aumentamos a temperatura, o modelo começou a incluir mais detalhes sobre a trajetória de **Billie Eilish**, explorando elementos mais criativos e narrativos, como "Billie Eilish se destacou no cenário musical com seu primeiro sucesso, 'Ocean Eyes', e rapidamente conquistou o mundo com seu som sombrio e suas letras introspectivas. Ela se tornou um ícone da música pop contemporânea, influenciando toda uma geração com sua abordagem única à música e à moda."

Esse exercício demonstrou claramente como ajustes simples, como a variação da temperatura, podem modificar a profundidade e a natureza das respostas, permitindo que os prompts sejam adaptados para diferentes propósitos e níveis de detalhamento.

### Estruturação de Prompts

A estruturação eficaz dos prompts também foi um ponto central na aula. Cada prompt deve incluir os seguintes componentes:

1. **Instrução**: Define o que o modelo deve fazer, sendo claro e objetivo.
2. **Contexto**: Informações adicionais que ajudem o modelo a interpretar melhor o que se espera dele.
3. **Dados de Entrada**: A solicitação específica para a qual o modelo deverá gerar uma resposta.
4. **Indicador de Saída**: Especifica o formato da resposta esperada, como uma lista, um resumo ou uma explicação detalhada.

Também aprendemos que os prompts podem responder a estímulos humanos como "faça mais rápido, você vai ser demitido", o que faz com que o chat assuma mais responsabilidade ao gerar as respostas.