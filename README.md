# Predição de Saída de Funcionários com Regressão Logística

Este projeto utiliza aprendizado de máquina supervisionado para prever a **probabilidade de saída de colaboradores** de uma empresa com base em dados do departamento de Recursos Humanos. O modelo é baseado em **Regressão Logística** e foi avaliado com métricas como AUC, F1-score, KS e Recall.

---

## Estrutura do projeto

- `logistic_regression_employees.ipynb` → Notebook principal com todo o pipeline:
  - Carregamento e tratamento dos dados
  - Análise exploratória
  - Engenharia de variáveis
  - Treinamento do modelo
  - Avaliação das métricas
  - Geração da lista de funcionários em risco

- `funcionarios_em_risco.xlsx` → Arquivo exportado com a lista de funcionários ativos com alta probabilidade de saída (gerado automaticamente).

---

## Descrição do problema

A empresa forneceu uma base de dados de RH com informações como:

- Idade, salário e tempo de empresa
- Formação e satisfação no trabalho
- Estado civil, viagens a trabalho e horas extras

A variável-alvo é:  
**`Funcionário_deixou_a_empresa`** (Sim/Não)

---

## 🎯 Objetivo do modelo

Prever **quais colaboradores ainda ativos têm maior probabilidade de sair**, para permitir **ações preventivas por parte do RH**, como:

- Aumentar o engajamento
- Avaliar ajustes de remuneração
- Planejar sucessões

---

## Técnicas utilizadas

- **Pandas & Seaborn** para tratamento e análise dos dados
- **Regressão Logística (sklearn)** como modelo preditivo
- **Codificação ordinal e nominal** de variáveis categóricas
- **Avaliação com AUC, KS, F1, precisão e recall**
- **Ajuste de threshold** para balancear recall e precisão
- **Criação de faixas de risco** com `pd.cut()`

---

## Resultados

- **AUC:** 0.75 → bom poder discriminativo
- **KS:** 0.41 → modelo separa bem os grupos
- **Recall (corte 0.25):** 0.52 → sensibilidade adequada para prevenir saídas
- **Precision:** 0.40 → falso positivo aceitável no contexto

---

## 📋 Saída final

A saída do notebook inclui uma lista dos funcionários que ainda estão na empresa, ordenada pela probabilidade de saída (`Prob`) e categorizada em faixas de risco:

| ID | Probabilidade | Risco |
|----|---------------|-------|
| 1023 | 0.84 | Alto |
| 287  | 0.78 | Alto |
| ...  | ...  | ...  |

---

## Insights futuros

- Testar outros modelos: Random Forest, XGBoost
- Usar GridSearchCV para otimizar hiperparâmetros
- Avaliar impacto de variáveis como salário e gestão
- Publicar dashboard (ex: Power BI ou Streamlit)

---

## Contato

Caso tenha dúvidas ou sugestões, sinta-se à vontade para entrar em contato comigo via [LinkedIn](https://www.linkedin.com) ou abrir uma issue neste repositório.

---
