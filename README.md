# Hello, World!
Olá 👋 equipe da DATUM!

Aqui é o Thiago Farias ([Perfil LinkedIn](https://www.linkedin.com/in/fariasthiago/)), e estou empolgado em apresentar o meu teste técnico para vaga de Engenheiro de Dados. Aqui está um guia detalhado sobre o projeto e suas funcionalidades.

## Conjunto de Dados
Para este projeto, escolhi o conjunto de dados do [Bike Store Relational Database](https://www.kaggle.com/datasets/dillonmyrick/bike-store-sample-database). O diagrama de Entidade e Relacionamento (ER) fornecido pode ser visto abaixo:

![Schema Bike Store](https://i.imgur.com/04YEup6.png)


## Camada Bronze

Nesta etapa, realizei a ingestão e preparação inicial dos dados do conjunto de dados do Kaggle. Abaixo está uma visão geral das etapas realizadas nesta camada:

1. **Autenticação Kaggle**: Autentiquei no Kaggle usando as credenciais fornecidas para acessar o conjunto de dados.
2. **Download e Armazenamento**: Baixei os arquivos do conjunto de dados do Kaggle e os armazenei no DBFS (Databricks File System) na camada bronze.
3. **Exportação para Delta Lake e Parquet**: Exportei os DataFrames para o formato Delta Lake e Parquet na camada bronze para facilitar o processamento e análise posterior.

Essas etapas são essenciais para preparar os dados para as próximas etapas de transformação e análise nas camadas subsequentes.

## Camada Silver

Na camada silver, realizei as seguintes transformações nos dados para prepará-los para análises mais aprofundadas:

1. **Conversão de Valores 'NULL'**: Iterei sobre cada DataFrame para substituir valores 'NULL', tornando a representação dos valores nulos mais consistente e legível.
2. **Verificação e Remoção de Duplicatas**: Verifiquei e removi duplicatas em todos os DataFrames para garantir a integridade dos dados.
3. **Transformações Específicas por DataFrame**:
   - **ORDERS**: Converti o campo "shipped_date" para o tipo Date e apliquei formatação.
   - **STAFFS**: Converti o campo "manager_id" de string para integer e criei a coluna "full_name" concatenando "first_name" e "last_name".
   - **CUSTOMERS**: Criei a coluna "full_name" concatenando "first_name" e "last_name", e converti a coluna "zip_code" para string.
   - **STORES**: Converti a coluna "zip_code" para string.
4. **Exportação para Delta Lake e Parquet**: Exportei os DataFrames para os formatos Delta Lake e Parquet na camada silver.

Essas transformações são fundamentais para limpar e preparar os dados para análises posteriores na camada gold.

## Camada Gold

Na camada gold, realizei análises avançadas dos dados para extrair insights valiosos. Abaixo estão algumas das análises e visualizações realizadas:

1. **Distribuição de Receita por Loja**:
   - Consulta SQL para calcular a receita total por loja.
   - Gráfico de barras mostrando a distribuição da receita por loja.

2. **Top 10 Clientes com Maior Gasto Total**:
   - Consulta SQL para identificar os 10 clientes que mais gastaram.
   - Gráfico de barras horizontais exibindo os 10 principais clientes com o maior gasto total.

3. **Distribuição de Receita por Ano e por Mês**:
   - Consultas SQL para calcular a receita total por ano e por mês.
   - Gráficos de barras mostrando a distribuição da receita ao longo do tempo, tanto por ano quanto por mês.

4. **Top 10 Produtos com Maior Receita Total**:
   - Consulta SQL para identificar os 10 produtos que geraram mais receita.
   - Gráfico de barras horizontais exibindo os 10 principais produtos com a maior receita total.

5. **Receita Total por Vendedor**:
   - Consulta SQL para calcular a receita total gerada por cada vendedor.
   - Gráfico de barras horizontais mostrando a receita total por vendedor.

6. **Análise RFV (Recência, Frequência, Valor)**:
   - Consulta SQL para segmentar os clientes com base na frequência de compra, na recência da última compra e no valor gasto.
   - Gráficos de contagem mostrando a distribuição dos clientes em diferentes segmentos.

7. **Média Móvel de 30 dias para Pedidos**:
   - Consulta SQL para calcular a média móvel de 30 dias para o número de pedidos.
   - Gráfico de linha mostrando a média móvel de 30 dias para cada loja ao longo do tempo.

8. **Média de Unidades Vendidas por Mês do Ano, por Categoria de Produto**:
   - Consulta SQL para calcular a média de unidades vendidas por mês para cada categoria de produto.
   - Gráfico de barras mostrando a média de unidades vendidas por mês do ano para cada categoria de produto.

Essas análises e visualizações fornecem uma compreensão mais profunda dos dados e podem orientar decisões estratégicas para a empresa.


## SQL Data Warehouse
Carreguei os dados para tabelas permanentes no banco de dados BikeStore para facilitar o acesso e análise por meio de consultas SQL e Power BI.

![DW](https://i.imgur.com/Hk6k6sA.png)

# Dashboards
- [Databricks](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1802048069101167/3500734898195404/2682982357215681/latest.html)
- [Power BI](https://app.powerbi.com/view?r=eyJrIjoiNTJlOGJkNmYtYTQ3OS00Mzc1LWJhYTEtM2Q0YTA1NmMzMWM5IiwidCI6ImFjYmJkZDFlLTE4YWYtNDIyMy04ZTdiLWMwZDk3MTllYTVmZiJ9&pageName=ReportSection)

![Dashboard](https://i.imgur.com/yjMC5Ax.png)

## Muito obrigado!

Agradeço pela oportunidade de apresentar este teste técnico e estou à disposição para quaisquer esclarecimentos adicionais ou discussões sobre o projeto. 