# 💳  ML + GenAI para Análise de Crédito
> Sistema inteligente de previsão de inadimplência que combina Machine Learning e GenAI para ajuste interativo de threshold, explicabilidade do modelo e suporte à tomada de decisão.

<div align="center">
  
[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg?style=flat&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.51+-red.svg?style=flat&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.6+-orange.svg?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Ollama](https://img.shields.io/badge/Ollama-phi3:mini-black.svg?style=flat&logo=ollama&logoColor=white)](https://scikit-learn.org)
[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-blue.svg?style=flat&logo=kaggle&logoColor=white)](https://scikit-learn.org)

![1220](https://github.com/user-attachments/assets/6f3f1c31-e485-41c2-a0b9-6f0cef2f7e67)

</div>

---

## 🎯 Overview

O projeto desenvolve uma classificação supervisionada com uma aplicação web interativa (Streamlit), permitindo a avaliação de risco de crédito por cliente, ajuste dinâmico do limiar de decisão e geração de explicações do modelo. A explicabilidade é realizada com SHAP, onde o papel do LLM é traduzir os resultados numéricos em insights compreensíveis ao modelo para tomada de decisão.

## 📂 Estrutura

```
CreditCard_Risk/
│
├── UCI_Credit_Card.csv     # Banco de dados utilizado
├── app.py                  # Aplicação web (Streamlit)
├── credit_EDA.ipynb        # [Extra] EDA - Análise Exploratória de Dados
├── explain.py              # Cálculo de explicabilidade (SHAP)
├── llm.py                  # Integração com LLM (Ollama)
├── prompts.py              # Engenharia de prompt
└── requirements.txt
```

## 🏗️ Arquitetura

O pipeline completo desenvolvido em **3 etapas principais**:

### 📊 1. Análise Exploratória & Feature Engineering
**Arquivo**: `notebooks/credit_EDA.ipynb`

- Análise exploratória profunda de 30.000 clientes
- Identificação de padrões de comportamento financeiro
- Criação de features derivadas:
  - `CREDIT_UTILIZATION`: Razão entre fatura e limite de crédito
  - `UTILIZATION_GROWTH_6M`: Tendência de crescimento do uso de crédito
  - `payment_ratio1`: Capacidade de pagamento da fatura
  - Séries temporais de 6 meses de histórico de pagamento

**Insights-chave**:
- Clientes com utilização de crédito > 80% têm risco 4.5x maior
- Histórico de pagamento dos últimos 3 meses é altamente preditivo
- Padrões demográficos (idade, escolaridade, ) correlacionam com risco

### 🤖 2. Modelagem Preditiva & Interface Interativa
**Arquivos**: `app.py`, `llm.py`, `explain.py`

- **Modelo**: Classificação binária (Random Forest)
- **Métricas**: Precision, Recall, F1-Score, ROC-AUC
- **Interface Streamlit**:
  - Upload de dados de clientes
  - Ajuste dinâmico de threshold (0-100%)
  - Visualização de métricas de negócio
  - Simulação de lucro/prejuízo

### 🧠 3. Explicabilidade com IA Generativa
**Arquivo**: `llm.py`, `prompts.py`

- Integrado à Interface Interativa
- **SHAP (SHapley Additive exPlanations)**: Análise de importância de features
- **LLM Local (Ollama)**: Geração de narrativas personalizadas: Tradução dos valores do SHAP em linguagem natural para o usuário.
- **Explicações contextualizadas**: 
  - Por que o crédito foi aprovado/negado?
  - Quais fatores mais influenciaram a decisão?
  - Recomendações para melhoria do score


---


### 📞 Contato
- **GitHub**: [liakruk](https://github.com/liakruk)
- **Linkedin**: [liakruk](https://www.linkedin.com/in/liakruk/)

---

## 🚀 Roadmap e Melhorias Futuras

Este projeto está em evolução contínua. Abaixo estão as melhorias planejadas com base em feedbacks da comunidade e estudos de aprofundamento técnico.

### 🏗️ Arquitetura & Engenharia
- [ ] **API First:** Expor o modelo via **FastAPI** para desacoplar o backend e facilitar integrações futuras.
- [ ] **Frontend Dedicado:** Desenvolvimento de interface própria (HTML/CSS/JS) consumindo a API para melhorar a UX.
- [ ] **Notificações Assíncronas:** Implementar envio de relatórios via WhatsApp ou E-mail (SMTP) em background tasks.

### 🧠 Data Science & IA Generativa
- [ ] **Otimização de Threshold:** Implementar lógica de threshold dinâmico (Relação Lucro vs. Custo do Falso Positivo).
- [ ] **Contexto Estatístico para LLM:** Enriquecer o prompt com métricas de distribuição (curtose, média, percentis) para reduzir alucinações.
- [ ] **Integração de LLM via API:** Migrar para modelos via API com free tier (ex: Groq/Llama 3) para produção.
- [ ] **Testes Locais:** Experimentar modelos leves (ex: Qwen 2.5 3B) para inferência local.

### ☁️ DevOps & Infraestrutura
- [ ] **Deploy em Nuvem:** Publicação da solução usando serviços como **Render** (Backend) e **Vercel** (Frontend).

---

*README inspirado no fork do [@faelp22](https://github.com/faelp22)*
