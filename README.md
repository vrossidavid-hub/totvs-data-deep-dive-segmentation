# Deep Dive em Bases + ETL (Oracle) + Segmentação de Clientes (RFM + Clustering)

Este projeto reúne um **deep dive nas bases de dados**, um fluxo de **extração via Oracle**, e uma etapa de **segmentação de clientes** usando **RFM + clusterização**. O foco é **reduzir redundâncias**, **facilitar relacionamento entre bases** e gerar **segmentos acionáveis** para decisões de negócio.

---

## 🎯 Objetivo

- Mapear e entender as bases envolvidas (campos, chaves e relacionamentos possíveis).
- Extrair dados a partir de um banco **Oracle** e gerar datasets analisáveis.
- Criar variáveis **RFM (Recency, Frequency, Monetary)** para segmentação.
- Aplicar **clusterização** (ex.: K-Means) e **interpretar perfis** por cluster.
- Gerar outputs finais (CSVs) com clusters prontos para uso em análises e ações.

---

## 🧠 Contexto do Deep Dive

Durante o diagnóstico, foram observados desafios típicos de ambientes com múltiplas bases:
- **Redundância de informações** e dificuldade de identificar “fonte de verdade”.
- **Campos/chaves ausentes** em algumas tabelas, dificultando joins.
- Necessidade de criar um caminho claro para **clusterização e relacionamento** entre bases.
- Preocupação com **custo e eficiência** (armazenamento/processamento em nuvem).

O documento de referência do diagnóstico está em:  
`docs/Deep Dive into Databases.docx` (recomendado converter para `.md` para facilitar leitura no GitHub).

---

## 🧩 O que foi entregue

### 1) Extração (Oracle → CSV)
- Notebook: `Challenge - Extração.ipynb`
- Conecta no Oracle via `oracledb`, executa queries e exporta datasets em CSV.

### 2) Segmentação RFM + Clusterização
- Notebooks de modelagem/clusterização por base:
  - `RFM- Base 1.ipynb`
  - `RFM - Base 2.ipynb`
  - `RFM - Base Complexa 1.ipynb`
  - `RFM - Base Complexa 2.ipynb`
  - `Box-Cox e K-Means 1.ipynb`
- Outputs finais (exemplos):
  - `Resultado - Base1.csv`
  - `Resultado - Base2.csv`
  - `Resultado - Base3.csv`

### 3) Histórico e análises auxiliares
- `historico.csv` + notebooks de análise do histórico para apoiar interpretação.

---

## 🔎 Metodologia (alto nível)

1. **Entendimento das bases**
   - Inventário de tabelas/arquivos
   - Mapeamento de colunas, chaves candidatas e relações possíveis
2. **Extração e preparação**
   - Consulta e exportação via Oracle
   - Limpeza e padronização de tipos/campos
3. **Feature engineering (RFM)**
   - Recency: tempo desde a última interação/compra
   - Frequency: quantidade de interações/compras
   - Monetary: valor total/médio (quando aplicável)
4. **Transformações**
   - Quando necessário: Box-Cox / Yeo-Johnson, normalização/padronização
5. **Clusterização**
   - Ex.: K-Means para gerar grupos
   - Avaliação com métricas/curvas (quando aplicável)
6. **Interpretação**
   - Perfil de cada cluster (ex.: “alto valor e recorrente”, “recente e pouco frequente”…)
   - Recomendações de ação por segmento

---

##
