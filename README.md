# README — AgentGeneratesSummariesForApplications

## 📌 Descrição do Projeto

Este projeto cria um **Agente Inteligente no Azure Foundry** capaz de:

* Ler um **arquivo PDF de edital** enviado pelo usuário.
* Identificar automaticamente **todas as áreas de conhecimento** citadas.
* Listar **tópicos e subtópicos** dessa área.
* Criar **flashcards completos**, incluindo:

  * Título
  * Subtítulo
  * Definição
  * Tipos e subtipos (com características)
  * Principais diferenças
  * Exceções
* Consultar fontes confiáveis da web (livros, sites jurídicos, universidades, materiais de concurso).

O agente combina:

* **Modelos do Foundry**
* **Parsing de PDF**
* **Pesquisa externa** (browser_search / web browsing)

---

## 🧠 Objetivo Geral

Automatizar todo o processo de estudo para editais de concurso, desde a leitura do documento até a entrega de flashcards detalhados.

---

## 🏗️ Arquitetura Geral do Fluxo

1. **Usuário envia o edital (PDF)** ao agente.
2. O Foundry extrai o texto do edital.
3. O agente identifica automaticamente **áreas de conhecimento**.
4. O agente gera uma **interface de seleção** para o usuário escolher uma área.
5. O agente cria estrutura hierárquica de tópicos e subtópicos.
6. O agente faz pesquisa em fontes confiáveis.
7. Gera **flashcards completos**.

---

## 📸 Prints do Fluxo e Execução


### Tela de configuração do agente no Foundry
<img width="1349" height="573" alt="image" src="https://github.com/user-attachments/assets/762c1ba2-047f-4d24-af98-8b34478bf02b" />


![Credenciais](sandbox:/mnt/data/c201844d-c1b2-4d9b-8154-ca296eaa612b.png)

### Execução do fluxo do agente

![Execução]
<img width="1215" height="560" alt="image" src="https://github.com/user-attachments/assets/ceb9966f-717d-4025-a65d-eea8fb4d7962" />


---

## 🔧 Configuração do Agent no Foundry

### ### 1. Criar o Agente

* Acesse o Azure Foundry → Agents
* Clique **Create Agent**
* Selecione **Conversational Agent**
* Habilite:

  * Bing Search (ou Web Browsing)
  * File Upload

---

## 📥 2. Prompt Completo do Agente (cole no "Agent Instructions")

```
Você é um agente para estudo de editais. Seu fluxo deve seguir **rigorosamente** estes passos:

1. Receber um PDF do usuário. Extraia todo o conteúdo.
2. Identifique automaticamente todas as **áreas de conhecimento** citadas.
3. Gere para o usuário uma interface com **caixa de seleção** contendo as áreas identificadas.
4. Quando o usuário escolher uma área, liste todos os **tópicos e subtópicos** relacionados.
5. Para cada tópico, pesquise em fontes confiáveis:
   - Livros
   - Sites jurídicos (STJ, STF, gov.br, senado, planalto)
   - Universidades
   - Portais de concurso
6. Com base nas fontes, gere **flashcards estruturados**:
   - Título
   - Subtítulo
   - Definição completa
   - Tipos e subtipos (se existirem)
   - Características de cada tipo
   - Diferenças importantes
   - Exceções
7. Após gerar todos os flashcards, envie-os para o WhatsApp do usuário via **Infobip WhatsApp API**.

Nunca invente leis ou conceitos. Cite bases sólidas.

---


---

## 🔗 Referências Oficiais

### **Foundry**

* Agents: [https://learn.microsoft.com/azure/ai-studio/agents](https://learn.microsoft.com/azure/ai-studio/agents)
* Browser Automation: [https://learn.microsoft.com/azure/ai-studio/browser-automation](https://learn.microsoft.com/azure/ai-studio/browser-automation)


Basta pedir!
