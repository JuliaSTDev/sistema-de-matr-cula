# 🎓 Sistema de Matrícula Inteligente - Cultura Inglesa

Este projeto apresenta uma arquitetura de **IA Conversacional de Alta Performance** desenvolvida para automatizar o funil de vendas e a conversão de matrículas. O sistema utiliza um modelo de **Orquestração de Agentes Especialistas**, integrando processamento de linguagem natural com sistemas de gestão empresarial (CRM).

---

## 🚀 Tecnologias e Ecossistema

* **Orquestração de Fluxo:** [n8n](https://n8n.io/) (Arquitetura orientada a eventos).
* **Inteligência Artificial:** Groq (Llama 3 / Mixtral) & LangChain (Engenharia de Prompt avançada).
* **Banco de Dados Relacional:** PostgreSQL (Gestão de leads, estados do funil e persistência).
* **Memória e Cache:** Redis (Gestão de contexto multi-turno e histórico de chat).
* **Integração Enterprise:** Conexão nativa com **CRM (Oracle)** para sincronização de dados de vendas.
* **Linguagens:** JavaScript (Lógica de negócios e tratamento de tempo/fuso) e SQL (Queries dinâmicas).

---

## 🧠 Arquitetura do Sistema: O "Orquestrador de Estados"

Diferente de chatbots tradicionais, este sistema opera como uma **Máquina de Estados**. O núcleo do sistema é um Orquestrador que decide, em tempo real, qual agente deve assumir a interação com base nos dados do banco:

1.  **Módulo de Identificação:** Verifica via PostgreSQL se o lead é novo ou recorrente.
2.  **Agentes Especialistas (Tools):**
    * **Agente de Sondagem:** Realiza a qualificação (BANT), coleta de documentos (CPF) e identificação de necessidades.
    * **Agente de Pitch:** Desenvolve argumentos de venda baseados na metodologia da escola.
    * **Agente de Agendamento:** Gerencia follow-ups automáticos caso o lead interrompa o contato.
3.  **Integração de CRM:** Todos os dados coletados (Nome, CPF, Motivação, Nível de Inglês) são injetados automaticamente no **CRM**, garantindo que a equipe comercial humana tenha visibilidade total do funil.

---

## 🛠️ Diferenciais Técnicos (Showcase para ADS)

### 1. Sincronização em Tempo Real com CRM
O sistema não apenas conversa; ele atua como um braço de entrada de dados. A integração com o CRM elimina o trabalho manual e garante que a "Receita" (Revenue) seja monitorada desde o primeiro "Oi".

### 2. Gestão de Contexto e Fuso Horário
Implementação de lógica customizada em JS para garantir que a IA respeite o fuso horário brasileiro (Brasília), enviando saudações e agendamentos de retorno precisos.

### 3. Blindagem de Regras de Negócio
Utilização de prompts estruturados para impedir a progressão no funil sem os requisitos mínimos (ex: proibição de exibição de preços antes da coleta do CPF e bairro de preferência).

---

## 🏗️ Roadmap de Desenvolvimento

- [x] Arquitetura de múltiplos agentes no n8n.
- [x] Integração de persistência via PostgreSQL e Redis.
- [x] Conexão com camada de CRM para sincronização de leads.
- [ ] Implementação de sistema de "Auto-Save" para evitar perda de dados parciais.
- [ ] Dashboard de análise de taxas de conversão entre fases (Sondagem -> Matrícula).

---

### 👩‍💻 Desenvolvedora
**Julia** *Desenvolvedora ADS*
