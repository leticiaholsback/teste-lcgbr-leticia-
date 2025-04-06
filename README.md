# Teste Técnico – Analista de Dados | Letícia dos Santos

## 📊 Account Monthly Balance Analysis

Este repositório apresenta as soluções desenvolvidas para o teste técnico da **LCGBR**, utilizando a plataforma **Google BigQuery**. O foco foi analisar dados relacionados à inadimplência e comportamento financeiro dos clientes, aplicando conceitos de engenharia e análise de dados.

---

## 👩‍💻 Tecnologias Utilizadas

- **Google BigQuery**
- **SQL**
- **Git & GitHub**
- **Looker Studio (Data Studio)**

---

## 🔄 Camadas de Dados

- **Raw:** Dados brutos extraídos diretamente da fonte (Data Warehouse).
- **Trusted:** Dados com tratamento de tipos, normalizações e limpeza de registros inconsistentes.
- **Refined:** Métricas e KPIs calculados e prontos para consumo analítico.

---

## 🗂️ Estrutura do Projeto

```plaintext
.
├── queries/             # Contém as queries SQL organizadas por camada e desafio
│   ├── raw/
│   ├── trusted/
│   └── refined/
│
├── insights/            # Interpretações analíticas dos desafios
├── datasets/            # Documentação das tabelas utilizadas
├── assets/              # Diagramas e imagens de apoio
└── README.md            # Documentação principal do projeto
````
---

## 📂 Datasets Utilizados

- **Projeto GCP:** `teste-lcgbr-leticia`
- **Dataset Raw:** `testelcgbrleticia`
- **Dataset Trusted:** `trusted_testelcgbrleticia`

---

## 🧩 Desafios

### 🔹 Desafio 1 – Perfil dos Inadimplentes 
📄[Query SQL]([queries/desafio_3.sql](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/main/refined_query_desafio)) | 📊 [Tabela Criada]((https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/main/bq-results-20250406-150135-1743951771621.csv))


> Objetivo: Compreender o perfil dos clientes inadimplentes com base em movimentações financeiras.

---

### 🔹 Desafio 2 – Risco de Inadimplência  
📄 [Query SQL](queries/desafio_2.sql) | 📊 [Análise e Insights](insights/desafio_2.md)

> Objetivo: Identificar possíveis clientes com risco de inadimplência.

---

### 🔹 Desafio 3 – Estratégias para Redução de Inadimplência  
📄 [Query SQL](queries/desafio_3.sql) | 📊 [Análise e Insights](insights/desafio_3.md)
> Objetivo: Propor ações baseadas em dados para reduzir a inadimplência no portfólio.

---

## 📌 Considerações Finais

Essa foi uma experiência valiosa, permitindo aplicar na prática conceitos de análise de dados com foco em impacto nos negócios.  
Acredito que dados bem tratados e interpretados são a chave para decisões estratégicas mais inteligentes.

Estou animada para contribuir com a equipe da **LCGBR**!

---


