# Desafio Telecom X parte 2

## Missão
Desenvolver um modelo preditivo capaz de prever quais clientes tem mais chances de cancelar os serviços

## Objetivos

<ul>
  <li>Preparar os dados para a modelagem</li>
  <li>Realizar análise de correlações entre variáveis</li>
  <li>Treinar dois ou mais modelos de correlação</li>
  <li>Avaliar o desempenho do modelo com métricas</li>
  <li>Interpretar os resultados</li>
  <li>Criar uma conclusão estratégica apontando os principais fatores que influenciam a evasão</li>
  
</ul>
Tecnologias e Ferramentas
<ul>
<li>Linguagem: Python</li>
<li>Manipulação de Dados: Pandas, NumPy</li>
<li>Visualização: Matplotlib, Seaborn, Yellowbrick</li>
<li>Machine Learning: Scikit-Learn (Random Forest, Logistic Regression, KNN, GridSearchCV)</li>
<li>Serialização: Pickle</li>
</ul>
Metodologia e Modelagem
O projeto seguiu as seguintes etapas:
<ul>
<li>Preparação dos Dados: Tratamento de variáveis categóricas com OneHotEncoder e remoção de identificadores irrelevantes (customerID).</li>
<li>Otimização: Uso de GridSearchCV para encontrar os melhores hiperparâmetros para o modelo Random Forest.</li>
<li>Tratamento de Desbalanceamento: Aplicação do parâmetro class_weight='balanced' para priorizar a identificação da classe minoritária (Churn).</li>
</ul>
Performance do Modelo Campeão (Random Forest)
O modelo final apresentou um equilíbrio sólido entre precisão e recall:
<ul>
<li>Acurácia Geral: ~80%</li>
<li>Recall (Classe Churn): Significativamente superior aos modelos base, garantindo que o negócio identifique a maioria dos clientes em risco.</li>
</ul>
Insights de Negócio (Relevância das Variáveis)

A análise das variáveis revelou os principais "gatilhos" de evasão na Telecom X:
<ul>
<li>Tipo de Contrato: Clientes com contrato Mês-a-Mês têm a maior taxa de saída.</li>

<li>Tecnologia: Utilizadores de Fibra Ótica apresentam maior risco que os de DSL, sugerindo necessidade de revisão da qualidade técnica ou estabilidade deste serviço.</li>

<li>Tempo de Casa (Tenure): Clientes nos primeiros 6 meses de contrato são extremamente voláteis.</li>
  
<li>Método de Pagamento: O uso de Cheque Eletrónico está fortemente correlacionado com o cancelamento.</li>
</ul>
Prova de Conceito (Testes com Novos Clientes)
O modelo foi testado com perfis fictícios, demonstrando alta precisão na identificação de perfis de risco:
<ul>
<li>Perfil Alto Risco: Previsão de 79.9% de chance de Churn (Contrato mensal + Fibra).</li>
<li>Perfil Fiel: Previsão de apenas 11.8% de chance de Churn (Contrato de 2 anos + Longo tenure).</li>
</ul>
