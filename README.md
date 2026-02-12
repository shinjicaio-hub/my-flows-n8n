# 🚀 Automação de Newsletter Híbrida (Cripto & Elevadores) com IA

Este repositório contém um workflow do **n8n** que gera e envia automaticamente uma newsletter matinal personalizada. O sistema combina dados financeiros em tempo real com curadoria técnica de notícias utilizando Agentes de IA (Groq/Llama 3).

## 📋 Como Funciona o Fluxo

O workflow é disparado diariamente às 08:00 e executa as seguintes etapas:

1.  **Coleta de Dados:**
    * **Cripto:** Busca o preço atual e variação de 24h de Bitcoin, Ethereum e Solana via API do CoinGecko.
    * **Notícias:** Captura as últimas notícias sobre "tecnologia de elevadores" via RSS Feed do Google News.
2.  **Curadoria com IA (Agente de Filtro):** * Utiliza o modelo `llama-3.1-8b` (via Groq) para analisar a lista de notícias e selecionar as 3 mais relevantes, descartando anúncios.
3.  **Redação (Agente Redator):**
    * Utiliza o modelo `llama-3.3-70b` para formatar o texto final.
    * Aplica lógica condicional para emojis (🚀 para alta, 📉 para baixa).
4.  **Entrega:** Envia o e-mail formatado via SMTP.

## 🛠️ Tecnologias Utilizadas

* **n8n**: Orquestração do workflow.
* **Groq (Llama 3.1 & 3.3)**: Inteligência Artificial para curadoria e escrita.
* **CoinGecko API**: Dados de mercado financeiro.
* **Google News RSS**: Fonte de notícias.

## 🔧 Configuração Necessária

Para rodar este projeto, você precisará configurar as seguintes credenciais no seu n8n:

* **Groq API**: Para os nós de IA.
* **SMTP**: Para o envio dos e-mails.

> [!IMPORTANT]
> Lembre-se de alterar o destinatário no nó "Send email" para o seu próprio endereço.

## 📂 Estrutura do Repositório

- `_workflows/newsletter/`: Contém o arquivo JSON para importação.
- `img/`: Screenshots do funcionamento do fluxo.
