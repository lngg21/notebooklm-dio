# Caderno Temático: Automação de Processos e Agentes de IA com n8n

> **Desafio DIO - Aprendizagem Ativa com IA e NotebookLM / Gemini Notebook**  
> Repositório criado para documentar a construção do Caderno Temático, englobando curadoria de fontes, engenharia de prompts, resolução de problemas (cicatrizes de aprendizado) e miniguia de estudo sobre o ecossistema do **n8n** e integração com **Inteligência Artificial**.

---

##  1. Contexto e Objetivos

### Assunto Escolhido
O tema selecionado para este projeto de estudo é o **Ecossistema n8n e Agentes de IA**. O n8n é uma das ferramentas *low-code/no-code* e *open-source* mais poderosas do mercado para automação de fluxos de trabalho, orquestração de APIs e construção de agentes autônomos baseados em LLMs (Large Language Models) e MCP (Model Context Protocol).

###  Objetivos de Estudo
1. **Compreensão Arquitetural:** Entender os blocos fundamentais do n8n (*Workflows, Nodes, Triggers, Flow Lines, Tool Box*).
2. **Implantação e Infraestrutura:** Dominar a execução local e em container via **Docker** e **Docker Compose**.
3. **Agentes de IA e Protocolos Modernos:** Mapear a integração de IA no n8n (*LangChain nodes, AI Agents, Memory, Vector Stores*) e o uso do protocolo **MCP (Model Context Protocol)**.
4. **Aprendizagem Ativa com IA:** Utilizar o Gemini Notebook / NotebookLM como parceiro de estudos para sintetizar conhecimentos, testar prompts estratégicos e gerar documentação técnica.

---

##  2. Curadoria de Fontes

Para garantir respostas precisas, fundamentadas e sem alucinações, foram selecionadas e carregadas **7 fontes de alta qualidade** (documentações oficiais e tutoriais práticos em texto/Markdown e vídeos):

| Fonte | Tipo | Descrição / Foco Principal |
| :--- | :--- | :--- |
| **Documentação n8n (Parte 1)** | Markdown (`.md`) | Governança, segurança, RBAC, gestão de segredos externos (Vault, Infisical) e versionamento via Git. |
| **Documentação n8n (Parte 2)** | Markdown (`.md`) | Catálogo abrangente de nós integrados (comunicação, bancos de dados, IA, gerenciadores de tarefas). |
| **Documentação n8n (Parte 3)** | Markdown (`.md`) | Guia de autenticação e credenciais (OAuth2, API Keys, Service Accounts e JWE). |
| **Curso N8N Gratuito Para Iniciantes 2026** | Vídeo (YouTube) | Fundamentos de automação com IA, webhooks e integração WhatsApp + Google Sheets. |
| **Build Your First AI Agent [2026]** | Vídeo (YouTube) | Construção de agentes de IA com memória conversacional e tabelas de dados nativas no n8n. |
| **Create n8n Workflows With Agents \| MCP** | Vídeo (YouTube) | Uso do Model Context Protocol (MCP) oficial para criação e edição de fluxos via linguagem natural. |
| **n8n will change your life as a developer...** | Vídeo (YouTube) | Visão geral do n8n auto-hospedado, concorrência com Zapier e casos de uso práticos. |

---

##  3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

A utilização da IA como ferramenta de aprendizagem ativa exigiu refinamentos contínuos nos prompts para extrair respostas concisas, diretas e acionáveis.

###  Perguntas Estratégicas Elaboradas

1. **Prompt 1 (Conceitual):**  
   > *"Pra começar a entender BEM como funciona o ecossistema do n8n, separei algumas perguntas, onde quero que você responda de forma objetiva. Para eu fazer algumas anotações: O que é e qual a funcionalidade do n8n? O que é workflow n8n? O que é o Node? Como funciona a tool box? O que é a flow line?"*  
   * **Objetivo:** Estabelecer a base teórica e criar anotações rápidas sem rodeios.

2. **Prompt 2 (Prático/Infraestrutura):**  
   > *"Como eu instalo n8n com docker na minha máquina?"*  
   * **Objetivo:** Obter um passo a passo executável do Docker CLI com explicação dos flags e mapeamento de volumes persistentes.

3. **Prompt 3 (Produtividade):**  
   > *"Quais são os principais atalhos usados no n8n?"*  
   * **Objetivo:** Mapear atalhos de teclado divididos por categorias (canvas, fluxo, nós e grupos) para acelerar a construção no editor.

4. **Prompt 4 (Documentação e Síntese):**  
   > *"Você consegue me ajudar gerando um readme.md sobre a experiência de aprendizagem e consolidando o miniguia para o desafio da DIO?"*  
   * **Objetivo:** Consolidar todo o aprendizado em um repositório estruturado no GitHub.

---

###  "Cicatrizes" de Aprendizado & Troubleshooting (O Raciocínio por Trás dos Resultados)

| Desafio / Dificuldade Encontrada | Causa Raiz | Solução / Ajuste no Prompt (Iteração) |
| :--- | :--- | :--- |
| **Respostas preliminares genéricas ou extensas** | Solagação de prompts vagos sem delimitadores formais. | **Ajuste:** Inclusão explícita da restrição *"responda de forma objetiva para anotações rápidas"* e divisão em tópicos numerados. |
| **Risco de alucinação sobre portas e comandos Docker** | Comandos Genéricos do Docker podem esquecer a persistência de dados no n8n. | **Ajuste:** Validação contra as fontes da documentação oficial (`-v n8n_data:/home/node/.n8n` e `-p 5678:5678`), garantindo persistência no volume SQLite/Postgres. |
| **Aprofundamento na integração de IA e MCP** | O ecossistema de IA do n8n evoluiu rápido em 2025/2026 com nós específicos de LangChain e MCP. | **Ajuste:** Cruzamento de dados entre o vídeo de MCP oficial e a documentação Markdown para diferenciar *Instance-level MCP* e o nó *MCP Server Trigger*. |

---

##  4. Miniguia de Estudo (Entrega Final)

### Resumos Estruturados do Assunto

#### A. O Ecossistema e Arquitetura do n8n
* **n8n:** Plataforma de automação de fluxos de trabalho *low-code/no-code* que permite conectar centenas de aplicativos e serviços via APIs.
* **Workflows & Nodes:** Um workflow é uma sequência lógica de automação. Cada bloco (node) representa um gatilho (*trigger*), uma ação (*action*) ou uma transformação de dados.
* **Interface Visual:** A *Tool Box* permite pesquisar e adicionar nós ao canvas, enquanto as *Flow Lines* (setas) conectam os nós e orientam o fluxo de dados em formato JSON.

#### B. Execução e Deployment com Docker
Para subir um ambiente local isolado e com persistência de dados:

```bash
docker run -d \
  --name n8n \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  -e TZ="America/Sao_Paulo" \
  -e GENERIC_TIMEZONE="America/Sao_Paulo" \
  n8nio/n8n
```
* Acesse via navegador em: `http://localhost:5678`

#### C. Agentes de IA e MCP (Model Context Protocol)
* **AI Agents no n8n:** Utilizam LangChain sob o capô para criar agentes conversacionais com memória (*Window Buffer Memory, Postgres Memory*) e acesso a ferramentas (*Tools*).
* **Model Context Protocol (MCP):** Protocolo aberto que permite a agentes de IA (como Claude Desktop, Open Code, Lovable) ler schemas, criar tabelas e manipular workflows diretamente na instância do n8n sem necessidade de colar JSON manualmente.

---

### Glossário de Conceitos Aprendidos

* **Workflow:** Conjunto de nós integrados que executam um processo automatizado de ponta a ponta.
* **Node (Nó):** Bloco básico do n8n responsável por uma função específica (Trigger, Action ou Transformação).
* **Trigger:** Nó inicial que dispara a execução do workflow em resposta a um evento (Webhook, Agendamento Cron, Formulário, Mensagem em Chat).
* **Webhook:** Endpoints HTTP expostos pelo n8n para receber notificações em tempo real de sistemas externos.
* **MCP (Model Context Protocol):** Padrão aberto de conexão entre modelos de IA e sistemas externos / ferramentas.
* **Tool Box:** Painel lateral do n8n para busca, seleção e adição de nós ao canvas.
* **Flow Line:** Linha visual que conecta a saída (*output*) de um nó à entrada (*input*) do seguinte.
* **Credentials:** Armazenamento seguro e criptografado de chaves de API, tokens OAuth2 e senhas no n8n.
* **Sticky Note:** Nota adesiva visual utilizada para documentar e organizar o canvas do workflow.

---

###  Conjunto de Prompts Reutilizáveis para Futuras Revisões

Abaixo estão prompts otimizados para reutilização em futuros estudos sobre n8n e automação com IA:

1. **Revisão de Arquitetura de IA:**
   > *"Como funciona a conexão entre o nó 'AI Agent', o 'Chat Model' (ex: OpenAI/Gemini) e uma 'Tool' customizada (como o Call n8n Workflow Tool) no n8n? Responda em tópicos objetivos com um diagrama textual."*

2. **Diagnóstico de Erros (Troubleshooting):**
   > *"Meu container do n8n no Docker não está salvando os fluxos após reiniciar. Qual pode ser a causa no mapeamento de volumes `-v` e como corrigi-lo no docker-compose.yml?"*

3. **Autenticação e Credenciais:**
   > *"Quais são as diferenças entre usar API Key e OAuth2 no n8n ao conectar serviços como Google Sheets e WhatsApp Business API, e como configurar o OAuth Redirect URL?"*

4. **Agentes Autônomos com MCP:**
   > *"Explique a diferença entre ativar o MCP a nível de instância (Instance-level MCP) e utilizar o nó individual 'MCP Server Trigger' em um workflow do n8n."*

---

##  Considerações Finais
Este projeto demonstrou como o uso orientado de ferramentas de IA (Gemini Notebook / NotebookLM) aliado à curadoria rigorosa de fontes acelera o aprendizado de tecnologias complexas como o n8n. 

Sinta-se à vontade para clonar este repositório, reutilizar os prompts e aplicar o miniguia em seus próprios estudos de automação! 🚀
