# Student Performance Factors: Análise Preditiva e BI 🎓

Este projeto investiga os determinantes do sucesso acadêmico, utilizando Python para modelagem estatística e Power BI para visualização interativa. O foco central foi transformar variáveis qualitativas em um simulador de cenários capaz de prever notas com base em comportamentos estudantis.

## 🧠 Engenharia de Dados e Machine Learning

O dataset original era composto majoritariamente por dados qualitativos. Para viabilizar a análise matemática, apliquei **Label Encoding**, convertendo categorias como envolvimento parental e qualidade do professor em escalas numéricas ordinais.

### Comparação de Modelos Preditivos
Para encontrar a melhor forma de prever o `Exam_Score`, comparei dois modelos distintos:

| Métrica | Regressão Linear | Random Forest |
| :--- | :--- | :--- |
| **R² (Coeficiente de Determinação)** | **0.7709** | 0.6650 |
| **Erro Médio Absoluto (MAE)** | - | 1.09 pontos |

A **Regressão Linear** obteve um desempenho superior, explicando aproximadamente **77% da variância das notas**. Isso indica que, neste conjunto de dados, os fatores de desempenho possuem uma relação predominantemente linear, onde o impacto de variáveis como horas de estudo e presença é direto e constante.

## 📐 O Modelo Matemático

Utilizando os coeficientes obtidos na Regressão Linear, foi possível isolar o impacto individual de cada variável. A equação que sustenta o simulador no Power BI é:

$$Exam\_Score = 61.45 + (0.29 \times Hours\_Studied) + (\dots)$$

Onde:
* **Intercepto (61.45):** A nota base estimada para um aluno com valores zerados nos preditores.
* **Coeficiente de Estudo (0.29):** Indica que, matematicamente, **cada hora adicional de estudo incrementa a nota final em 0.29 pontos**, mantendo os demais fatores constantes.

## 📊 Pilares de Desempenho e BI

A análise de correlação de Pearson revelou os "motores" do desempenho acadêmico. Como demonstrado no gráfico abaixo, a **Presença Escolar (0.58)** e as **Horas de Estudo (0.45)** são os fatores com maior poder preditivo.

![Mapa de Correlação de Pearson](correlation_plot.png)

### Dashboard Interativo
O relatório foi desenhado em um padrão *Teal & Orange* para facilitar a leitura de métricas de sucesso vs. risco:

1. **Visão Geral e IA:** Utiliza o motor de IA do Power BI (*Key Influencers*) para validar as descobertas do Python, identificando que a motivação e o suporte familiar potencializam os ganhos das horas de estudo.
2. **Simulador What-If:** Implementado via DAX, permite que gestores escolares simulem o impacto de intervenções pedagógicas. Ao ajustar a carga horária de estudo, o dashboard recalcula em tempo real a projeção da nota baseando-se no coeficiente de **0.29** derivado do modelo de Machine Learning.

---
## 🛠 Tecnologias
* **Python:** Scikit-Learn, Pandas (Modelagem estatística).
* **Power BI:** DAX, Parâmetros de Campo, Modelagem Preditiva.
