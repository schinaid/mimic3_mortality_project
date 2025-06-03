# 🏥 MIMIC-III Mortality Analysis and Clinical Notes Modeling

Este repositório apresenta um pipeline completo de ciência de dados para análise exploratória e modelagem preditiva utilizando notas clínicas do banco de dados MIMIC-III. O foco é explorar o potencial do Processamento de Linguagem Natural (PLN) aplicado a sumários de alta hospitalar para prever mortalidade pós-alta.

---

## 📊 Objetivos

- Realizar análises descritivas dos dados sociodemográficos e clínicos.
- Extrair e estruturar informações relevantes de notas clínicas utilizando NLP.
- Identificar agrupamentos (clusters) de pacientes com base em sumários clínicos.
- Desenvolver modelos de predição de mortalidade hospitalar a partir de textos.
- Integrar dados laboratoriais com notas para análises temporais e interpretativas.

---

## 📁 Estrutura do Projeto

mimic3_mortality/
├── data/ # Dados brutos do MIMIC-III
│ └── Mimic-3_patients/
│ ├── ADMISSIONS/ # Admissões hospitalares
│ ├── NOTEEVENTS/ # Notas clínicas
│ ├── LABEVENTS/ # Dados laboratoriais
│ └── ... # Demais tabelas do MIMIC-III
│
├── notebooks/ # Notebooks de análise e modelagem
│ ├── 01_visualizacao_geral.ipynb
│ ├── 02_extracao_notas_clinicas.ipynb
│ ├── 03_nlp_scispacy_entidades.ipynb
│ ├── 04_clusterizacao_notas.ipynb
│ ├── 05_mortalidade_texto_modelo.ipynb
│ ├── 06_clinicalbert_classificacao.ipynb
│ ├── 07_analise_temporal_notas.ipynb
│ ├── 08_integracao_labs_notas.ipynb
│ └── figures/ # Visualizações geradas
│ └── *.png
│
├── models/ # Modelos treinados e vetorizadores
│ ├── bert-base-uncased/
│ ├── discharge_summaries_labeled.csv
│ └── *.pkl
│
├── processed/ # Dados prontos para modelagem
│ └── *.csv
│
├── mimic3_mortality/ # Módulos do projeto
├── tests/ # Testes de unidade
├── pyproject.toml # Dependências com Poetry
├── poetry.lock # Lockfile do ambiente
└── README.md 


---

## 📚 Fonte dos Dados

Os dados utilizados foram disponibilizados publicamente no Kaggle:

🔗 [MIMIC-III Kaggle Dataset](https://www.kaggle.com/datasets/asjad99/mimiciii)

**Atenção:** os dados são uma réplica parcial da base original MIMIC-III, adaptados para uso educacional. Para acesso ao banco completo, é necessário registro via [PhysioNet](https://physionet.org/).

---

## 🧠 Tecnologias e Bibliotecas

- Python 3.10+
- Scikit-learn
- Pandas / NumPy
- SciSpacy (`en_core_sci_sm`)
- BERT (`bert-base-uncased`)
- Matplotlib / Seaborn
- Poetry (para gerenciamento de ambiente)

---

## 🚀 Execução do Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/mimic3_mortality.git
   cd mimic3_mortality

Instale as dependências com Poetry:
poetry install

Execute os notebooks na pasta notebooks/ em ordem numérica (01 a 08) para reproduzir todas as etapas da análise.

Resultados
Agrupamento de pacientes com base nos sumários de alta (5 clusters clínicos identificados)

Extração de entidades médicas com SciSpacy

Modelo de regressão logística com embeddings BERT alcançando boa performance (AUC, sensibilidade, matriz de confusão)

Análise temporal de óbitos pós-alta revelando padrões críticos de risco


Este projeto é de uso educacional e acadêmico. Os dados são de acesso público, respeitando os termos de uso do MIMIC-III e do Kaggle.

Johnson AEW, et al. (2016). MIMIC-III, a freely accessible critical care database. Scientific Data.

Neumann M, et al. (2019). SciSpacy: Fast and Robust Models for Biomedical NLP. arXiv.

Devlin J, et al. (2018). BERT: Pre-training of Deep Bidirectional Transformers. arXiv.

Pedregosa F, et al. (2011). Scikit-learn: Machine Learning in Python. JMLR.
