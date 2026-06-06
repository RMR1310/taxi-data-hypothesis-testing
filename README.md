# Análise do Mercado de Táxis de Chicago  
## Web Scraping, Limpeza de Dados, Exploração e Teste de Hipóteses

## Objetivo do Projeto
Este projeto tem como objetivo coletar, limpar e analisar dados de corridas de táxi em Chicago, avaliando:

- a concentração de mercado entre empresas,  
- a distribuição de corridas por bairros,  
- e o impacto do clima na duração das viagens.

O trabalho combina **web scraping**, **tratamento de dados**, **análise exploratória** e **teste estatístico formal**.

---

## Coleta e Preparação dos Dados

### **1. Web Scraping**
- Acesso à página HTML com `requests`  
- Extração da tabela com `BeautifulSoup`  
- Leitura estruturada usando `pd.read_html`  
- Conversão de colunas para tipos adequados (ex.: `datetime`)  
- Limpeza de valores nulos e renomeação de colunas  
- Salvamento em CSV para reutilização

### **2. Carregamento e Inspeção**
- Leitura dos arquivos CSV (`df_companies`, `df_neighborhoods`)  
- Inspeção inicial com `df.head()`  
- Seleção por índice com `.iloc`  
- Filtros condicionais com `.loc`  
- Seleção de colunas específicas com `[['col1', 'col2']]`  
- Combinação de filtros booleanos e intervalos de datas

---

## Análise das Empresas de Táxi

Foram analisadas **64 empresas** nos dias **15 e 16 de novembro de 2017**.

### **Principais Resultados**
- **Flash Cab** lidera com aproximadamente **19,5 mil corridas**  
- **Taxi Affiliation Services** e **Medallion Leasing** superam **10 mil corridas** cada  
- **Yellow Cab** e **Taxi Affiliation Service Yellow** também aparecem entre as maiores  
- A maioria das empresas menores possui **menos de mil corridas**

### **Conclusão**
O mercado é **altamente concentrado**, com poucas empresas dominando a maior parte das viagens.

---

## Análise dos Bairros

Os dados mostram forte concentração de corridas em poucos bairros.

### **Destaques**
- **Loop** e **River North** somam **mais de 20 mil corridas**  
- Os demais bairros do Top 10 apresentam valores menores, mas ainda relevantes

### **Conclusão**
A demanda é fortemente centralizada em regiões comerciais e de grande fluxo.

---

## Teste de Hipótese — Duração das Corridas aos Sábados Chuvosos

### **Hipóteses**
- **H₀:** A duração média das corridas do Loop para O’Hare **não muda** em sábados chuvosos  
- **H₁:** A duração média **muda** nesses dias  

### **Metodologia**
- Comparação entre duas amostras independentes:
  - corridas em sábados chuvosos  
  - corridas nos demais dias  
- Teste estatístico: **t de Student para duas amostras independentes**  
- Nível de significância: **5%**

### **Resultado**
- p‑valor ≈ **6.7e‑12**  
- Muito menor que 0,05

### **Conclusão**
Rejeitamos **H₀**.  
A duração média das corridas **difere significativamente** entre sábados chuvosos e dias de clima normal.

---

## Conclusão Geral do Projeto

O projeto demonstra:

- Pipeline completo de **web scraping + limpeza de dados**  
- Forte **concentração de mercado** entre empresas de táxi  
- Alta demanda em **Loop** e **River North**  
- Evidência estatística de que o **clima afeta a duração das corridas**

A análise fornece uma visão clara do comportamento do mercado de táxis em Chicago e dos fatores que influenciam a operação.

---

## Tecnologias Utilizadas
- Python  
- Requests  
- BeautifulSoup  
- Pandas / NumPy  
- SciPy (teste t)  
- Jupyter Notebook  

---

## Estrutura do Repositório
