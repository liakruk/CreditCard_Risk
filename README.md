# 💳  ML + GenAI para Análise de Crédito
> Ferramenta de previsão de inadimplência que combina Machine Learning e GenAI para ajuste interativo de threshold, explicabilidade do modelo e suporte à tomada de decisão.

<div align="center">
  
[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg?style=flat&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.51+-red.svg?style=flat&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.124+-green.svg?style=flat&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.6+-orange.svg?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Ollama](https://img.shields.io/badge/Ollama-phi3:mini-black.svg?style=flat&logo=ollama&logoColor=white)](https://scikit-learn.org)
[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-blue.svg?style=flat&logo=kaggle&logoColor=white)](https://scikit-learn.org)

<h3>Demonstração do projeto</h3>

![1220](https://github.com/user-attachments/assets/6f3f1c31-e485-41c2-a0b9-6f0cef2f7e67)

</div>

---

## 🎯 Overview

O projeto combina classificação supervisionada com uma aplicação web interativa (Streamlit), permitindo a avaliação de risco de crédito por cliente, ajuste dinâmico do limiar de decisão e geração de explicações do modelo. A explicabilidade é realizada com SHAP, onde o papel do LLM é traduzir os resultados numéricos em insights compreensíveis ao modelo para tomada de decisão.

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

---
