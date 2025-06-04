# 🤖 Chatbot Automatizado com n8n

Projeto de criação de um chatbot inteligente utilizando a plataforma **n8n** para automação de fluxos de trabalho, atendimento ao cliente e integração com múltiplos canais de comunicação.

![n8n logo](https://n8n.io/images/n8n-logo.svg)

---

## 🧠 Sobre o Projeto

Este projeto tem como objetivo demonstrar a criação de um chatbot automatizado utilizando o **n8n**, com foco em:

- Atendimento inicial a clientes.
- Qualificação de leads.
- Integração com sistemas externos (Pontta, Gosac).
- Tomada de decisões com base em regras configuráveis.

> 💡 O chatbot foi implementado em uma empresa de móveis planejados, ajudando a otimizar o tempo da equipe comercial e padronizar o atendimento.

---

## 🛠️ Tecnologias Utilizadas

- [n8n](https://n8n.io/) – Plataforma de automação low-code
- Webhook
- PostgreSQL
- Google Drive
- WhatsApp (via API de terceiros)
- JavaScript (scripts personalizados)
- JSON para tratamento de dados

---

## 🔄 Fluxo do Chatbot

```mermaid
graph TD
A[Mensagem do usuário] --> B[Webhook n8n]
B --> C[Debounce de mensagens]
C --> D{Qual estado do cliente? Novo? Existente?}
D -- Sim --> E[Coleta e registro usuário do PostgreSQL]
D -- Não --> F[Verifica se passou pela triagem]
E --> G[Envia id do template correspondente]
F --> G[Envia mensagem de reconhecimento]
G --> H[Cria pasta no driver para o usuário]
H --> I[Cria um atendimento no Pontta com rodízio de atendentes]

## 🧭 Fluxograma do Chatbot

Abaixo está o fluxograma principal do chatbot desenvolvido no n8n:

![Fluxograma do chatbot](docs/imagens/fluxograma-chatbot.png)
