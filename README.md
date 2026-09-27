# MVP de Engenharia de Dados — Pokémon Challenge

Este projeto foi desenvolvido como MVP da disciplina de **Engenharia de Dados**, com o objetivo de construir um pipeline de dados ponta a ponta utilizando **Databricks, PySpark, SQL e Delta Lake**. Focado na construção da infraestrutura necessária para ingestão, tratamento, validação, modelagem e disponibilização dos dados para consumo analítico.

## Arquitetura

O pipeline segue os princípios da **arquitetura Medallion**:

**CSV → Bronze → Silver → Gold → Análises**

* **Bronze:** ingestão e preservação dos dados de origem;
* **Silver:** padronização, tipagem e validação dos dados;
* **Gold:** modelagem e disponibilização dos dados para consumo analítico.

A camada Gold é composta pelas tabelas:

* `dim_pokemon`
* `fact_battles`
* `agg_pokemon_performance`

## Perguntas de Negócio

O projeto busca responder às seguintes perguntas:

1. Pokémon com maior `Speed` apresentam maior taxa de vitória?
2. Quais atributos mais diferenciam vencedores e perdedores?
3. Pokémon `Legendary` apresentam taxa de vitória diferente dos demais?
4. Como a taxa de vitória varia entre as gerações?
5. Quais Pokémon apresentam as maiores taxas de vitória considerando um número mínimo relevante de batalhas?

## Tecnologias

* Databricks Free Edition
* Apache Spark / PySpark
* Spark SQL
* Delta Lake
* Python

## Notebooks

| Notebook              | Descrição                                       |
| --------------------- | ----------------------------------------------- |
| `01_ingestion_bronze` | Ingestão dos CSVs e construção da camada Bronze |
| `02_bronze_to_silver` | Padronização, tipagem e validação dos dados     |
| `03_silver_to_gold`   | Modelagem e construção das tabelas Gold         |
| `04_data_analysis`    | Consultas e análises das perguntas de negócio   |

## Principais Resultados

As análises indicaram associação entre **Speed e desempenho nas batalhas**, além de diferenças relevantes entre os atributos médios de vencedores e perdedores. Pokémon classificados como **Legendary** também apresentaram maior taxa de vitória no conjunto analisado.

A infraestrutura desenvolvida permite que os dados tratados da camada Gold sejam utilizados futuramente como fonte para aplicações analíticas ou modelos de Machine Learning.

## Documentação

A documentação completa do projeto, incluindo arquitetura, catálogo de dados, regras de qualidade, evidências da execução e análise dos resultados, está disponível em:

`docs/MVP_Data_Engineering.pdf`
