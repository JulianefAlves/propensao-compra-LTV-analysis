# propensao-compra-LTV-analysis

# Projeto de Inteligência de Dados: Predição de LTV e Segmentação de Clientes

Este projeto foi desenvolvido como parte do curso de Ciência de Dados, com o objetivo de criar um modelo estatístico e de aprendizado de máquina para prever o valor do ciclo de vida do cliente (LTV) e realizar a segmentação de base para estratégias de marketing.

## 1. Coleta e Preparação de Dados
A base de dados utilizada consiste em registros transacionais de um e-commerce. O processo de preparação incluiu:
* **Limpeza:** Remoção de registros sem identificação de cliente (`CustomerID`) e exclusão de transações com quantidades negativas (devoluções/cancelamentos).
* **Feature Engineering:** Agrupamento de dados por cliente para calcular a Recência, Frequência e o Valor Total gasto (Monetário).
* **Padronização:** Normalização de campos de texto (Países) e criação da métrica de faturamento por linha (`TotalSum`).

## 2. Modelagem e Avaliação
Para solucionar o problema de negócio, foram implementadas duas frentes de modelagem:

### Regressão (Predição de LTV)
* **Algoritmo:** Random Forest Regressor (Baseado em Árvores de Decisão).
* **Performance:** O modelo alcançou um **R² Score de 91,73%**, indicando uma altíssima precisão na explicação da variabilidade do faturamento.
* **Métrica de Erro:** O Erro Médio Absoluto (**MAE**) foi de **$162,30**, um valor controlado considerando a escala de compras da base.

### Agrupamento (Segmentação de Clientes)
* **Algoritmo:** K-means (Aprendizado não supervisionado).
* **Resultado:** A base foi segmentada em três grupos estratégicos:
    1.  **Ouro (Alto Valor):** Clientes com faturamento médio de ~$3.183.
    2.  **Prata (Médio Valor):** Clientes com faturamento médio de ~$1.637.
    3.  **Bronze (Baixo Valor):** Clientes com faturamento médio de ~$654.

## 3. Conclusões e Resultados
A análise demonstra que o uso de modelos de árvores e técnicas de agrupamento permite uma visão clara sobre a saúde financeira da base de clientes. 
* A identificação do segmento **Ouro** permite ações de fidelização personalizadas (Customer Success).
* A precisão do modelo de regressão oferece segurança para a projeção de receitas futuras e planejamento de estoque.
* A solução entrega uma visualização clara dos resultados, facilitando a comunicação entre a área técnica e os stakeholders de negócio.

---
**Tecnologias Utilizadas:** Python, Pandas, Scikit-learn, Matplotlib e Seaborn.
