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

## ✅ Conclusão

Todas as etapas foram realizadas conforme solicitado, com atenção ao detalhamento da base de dados, limpeza, enriquecimento, criação de métricas e preparação para visualização. A entrega final permite fácil replicação e leitura dos dados por áreas técnicas e de negócios.

---


## 📈 Dashboard

O dashboard desenvolvido apresenta:

- Evolução do saldo das contas ao longo do tempo.
- Análise detalhada das transações PIX.
- Identificação de padrões e possíveis anomalias nos dados.

## 📝 Observações

- Os dados utilizados são fictícios e foram fornecidos exclusivamente para fins deste teste técnico.
- As análises e insights apresentados refletem as técnicas e abordagens adotadas durante o desenvolvimento do teste.

## 📧 Contato

Para mais informações ou dúvidas, entre em contato:

- **Nome**: Letícia dos Santos
- **E-mail**: [leticiaholsback@gmail.com)
- **LinkedIn**: [https://www.linkedin.com/in/leticia-santos-33a15a150/)

---

*Este repositório foi desenvolvido como parte do processo seletivo para a posição de Analista de Dados Jr. na LCGBR.*

🧩 Desafios
🔹 Desafio 1 – Obter saldo mensal das contas
📄 Query SQL
📊 Tabela Criada

Objetivo: Gerar uma tabela com o saldo mensal de cada conta, utilizando a movimentação via PIX como base.

🔹 Desafio 2 – Criar análise de performance utilizando janela deslizante (sliding window)
📄 Query SQL
📊 Tabela Criada

Objetivo: Criar indicadores de performance considerando janelas móveis de 1 e 3 meses.

🔹 Desafio 3 – Propor métricas para acompanhamento da performance do PIX
📄 Query SQL - Métricas por ID
📊 Tabela Criada

Objetivo: Sugerir e construir um conjunto de métricas que possibilitem o acompanhamento da performance do PIX entre os clientes.

---

## 📌 Considerações Finais

Essa foi uma experiência valiosa, permitindo aplicar na prática conceitos de análise de dados com foco em impacto nos negócios.  
Acredito que dados bem tratados e interpretados são a chave para decisões estratégicas mais inteligentes.



---


