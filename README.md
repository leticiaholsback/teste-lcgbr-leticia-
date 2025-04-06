# Teste Técnico – Analista de Dados | Letícia dos Santos

## 📊 Account Monthly Balance Analysis

Este repositório apresenta as soluções desenvolvidas para o teste técnico da **LCGBR**, utilizando a plataforma **Google BigQuery**. O foco foi analisar dados relacionados à inadimplência e comportamento financeiro dos clientes, aplicando conceitos de engenharia e análise de dados.

---

## 🔍 Escopo do Desafio

O desafio técnico propôs as seguintes entregas:

1. **Consulta SQL para saldo mensal das contas**
2. **Consulta SQL com cálculos de janela (sliding window) para análise de performance**
3. **Proposta de métricas para acompanhamento da performance de PIX**
4. **Esboço de dashboard com base nas métricas sugeridas**
5. **(Bônus)** Criação de dashboard com ferramenta de visualização de dados

---   

## 👩‍💻 Tecnologias Utilizadas

- **Google BigQuery**
- **SQL**
- **Git & GitHub**
- **Looker Studio (Data Studio)**

---

## 🔄 Camadas de Dados

- **Raw** → teste-lcgbr-leticia.testelcgbrleticia (Dados brutos extraídos diretamente da fonte)-

- **Trusted** → teste-lcgbr-leticia.trusted_testelcgbrleticia (Dados com tratamento de tipagem e limpeza de registros)

- **Refined**  → teste-lcgbr-leticia.refined_teste_lcgbr_leticia (Métricas e KPIs calculados e prontos para consumo no DataStudio e com aplicações dos contextos do teste)

---


## 📂 Estrutura do Repositório

- `1.criacao_projeto_GCP/`: Scripts e instruções para a criação do projeto no Google Cloud Platform.
- `2.incluindo_tabelas/`: Scripts SQL para a inclusão e manipulação de tabelas no BigQuery.
- `3.refined_query_Contexto_de_Negócio_1/`: Consultas refinadas relacionadas ao primeiro contexto de negócio.
- `4.trusted_queries/`: Consultas SQL confiáveis utilizadas nas análises.
- `Dashboard_LGCBR/`: Recursos relacionados ao dashboard desenvolvido.
- `README.md`: Este arquivo.
- `Teste técnico - Analista de dados.pdf`: Documento original do teste técnico.
- Arquivos CSV (`leticia.account_monthly_balance.csv`, `leticia.pix_refined.csv`, etc.): Conjuntos de dados utilizados nas análises.
- `raw_leticia.jpg`: Imagem representativa dos dados brutos.

---

## 🗂️ Organização da Solução

### 🧱 Camadas de Dados Criadas no BigQuery

- `raw`: ingestão dos dados originais
- `trusted`: limpeza, padronização e inclusão de colunas-chave como `id`
- `refined`: estrutura final para análise e visualização, com métricas agregadas e tratadas

Exemplo de tabelas refinadas:
- `refined_teste_lcgbr_leticia.account_monthly_balance`
- `refined_teste_lcgbr_leticia.refined_pix_metrics_by_id`
- `refined_teste_lcgbr_leticia.refined_pix_summary`

---


## 📊 Análises Realizadas

1. **Account Monthly Balance Analysis**: Análise do saldo mensal das contas, identificando padrões de comportamento financeiro dos clientes.
2. **PIX Transactions Analysis**: Estudo das transações PIX, incluindo métricas como número de transações, valores envolvidos e detecção de outliers.
3. **Dashboard Interativo**: Desenvolvimento de um dashboard no Google Data Studio para visualização das principais métricas e insights obtidos.

---

## 🧾 Consultas SQL Desenvolvidas

### 1. **Saldo Mensal por Conta**
Consulta criada para trazer o saldo mensal agrupado por `account_id`, considerando entradas e saídas via PIX.

### 2. **Sliding Window (Janela Móvel)**
Consulta com cálculo de métricas percentuais de movimentação, comparando os últimos 1 e 3 meses, segmentado por mês e `account_id`.

### 3. **Métricas de PIX por ID**
Criação da tabela `refined_pix_metrics_by_id`, com:
- Total de transferências por conta
- Percentuais de variação por janela móvel
- Participação por mês
- Flag de outlier baseado no desvio padrão

---

## 📊 Métricas Sugeridas

- Total de transações por conta e por mês
- Valor total movimentado por tipo (`pix_in`, `pix_out`)
- Variação percentual de transações em janelas móveis (1 e 3 meses)
- Participação da conta no total do mês
- Flag de outlier por comportamento atípico
- Status das transações (`completed`, `failed`, etc.)
- Agregações semanais (valor médio e contagem)

---

## 🧾 Visualização (Bônus)

Um dashboard no **Looker Studio (ex-Data Studio)** foi criado para apresentar:

- Evolução mensal das transações por tipo
- Comparativo entre contas
- Detecção de outliers
- Filtros interativos por status, tipo, mês e conta

> 🎯 O foco do dashboard é entregar visões estratégicas e insights para áreas de negócio e prevenção a fraudes.

---

🧩 Desafios
### Desafio 1 – Obter saldo mensal das contas

📄 **Query SQL:**  
[query1_BusinessContext2](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/e4747cc62cf543614b66fbac8222d70859780e50/2.query1_%20BusinessContext2)

📊 **Tabela refinada gerada:**  
[bq-results-20250406-150135-1743951771621.csv](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/f12515fcd90fd31f0ca35643c3ebb310a6cbca43/leticia.account_monthly_balance.csv)

Essa tabela contém o saldo mensal agregado por conta, conforme solicitado no Desafio 1.

---

### 🔹 Desafio 2 – Criar análise de performance utilizando janela deslizante (sliding window)

📄 **Query SQL**: [5.query_slidingWindow](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/ecf49ffdf8c5dd9ae68440e27262e610871d09a9/5.query_slidingWindow)  
📊 **Tabela Criada**: [leticia.sliding_window_calculations.csv](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/ad7b2f7cfd921e3456cf76ab4e078f7bda546bc7/leticia.sliding_window_calculations.csv)

**Objetivo:**  
Criar indicadores de performance com base em janelas móveis (sliding windows) de 1 e 3 meses, utilizando transações PIX.

**Resumo da lógica:**  
A query utiliza funções de janela (`SUM(...) OVER (...)`) para calcular, por `account_id` e `account_type`, a soma dos valores e a contagem das transações PIX nos últimos 1 e 3 meses, com base no campo `pix_month`.

---
---

### 🔹 Desafio 3 – Criar resumo mensal das transações PIX

📄 **Query SQL**: [3.query_refined_pix_summary](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/main/3.query_refined_pix_summary)  
📊 **Tabela Criada**: [leticia.refined_pix_summary.csv](https://github.com/leticiaholsback/teste-lcgbr-leticia-/blob/958d18e539afe0148fd2cbc8f55338f273925ecd/leticia.refined_pix_summary.csv)

**Objetivo:**  
Consolidar as transações PIX em um resumo por mês, calculando:

- Total de transações (`pix_count`)
- Soma total dos valores transacionados (`total_pix_value`)
- Valor médio por transação (`avg_pix_value`)

**Resumo da lógica:**  
A query agrupa os dados por `pix_month` e aplica funções de agregação (`COUNT`, `SUM` e `AVG`) para gerar o resumo mensal das movimentações realizadas via PIX.

---


## 📈 Dashboard

O dashboard desenvolvido apresenta:

- Evolução do saldo das contas ao longo do tempo.
- Análise detalhada das transações PIX.
- Identificação de padrões e possíveis anomalias nos dados.

---

## 📝 Observações

- Os dados utilizados são fictícios e foram fornecidos exclusivamente para fins deste teste técnico.
- As análises e insights apresentados refletem as técnicas e abordagens adotadas durante o desenvolvimento do teste.

---

## 📧 Contato

Para mais informações ou dúvidas, entre em contato:

- **Nome**: Letícia dos Santos
- **E-mail**: [leticiaholsback@gmail.com)
- **LinkedIn**: [https://www.linkedin.com/in/leticia-santos-33a15a150/)

---

*Este repositório foi desenvolvido como parte do processo seletivo para a posição de Analista de Dados Jr. na LCGBR.*


