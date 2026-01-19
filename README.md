# 📊 Pipeline de Engenharia de Dados: Análise de Hospedagem

Este projeto implementa um pipeline completo de **Data Wrangling** (tratamento de dados) utilizando Python e Pandas. O foco é a ingestão, limpeza e estruturação de dados brutos de imóveis para aluguel (estilo Airbnb), transformando arquivos JSON aninhados em datasets prontos para análise e Machine Learning.

## 📂 Estrutura do Repositório

A organização do projeto segue boas práticas de engenharia de dados:

- `projeto-final.ipynb`: Jupyter Notebook contendo todo o código de ETL (Extração, Transformação e Carga).
- `dados/`: Pasta recomendada para armazenar os datasets brutos.
  - `dados_hospedagem.json`: Dados detalhados dos imóveis (descrições, comodidades, preços).
  - `moveis_disponiveis.json`: Séries temporais de disponibilidade e valores por data.

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Pandas**: Manipulação avançada de DataFrames.
- **NumPy**: Operações numéricas e conversão de tipos de dados.
- **JSON**: Processamento de estruturas de dados aninhadas.

## ⚙️ Etapas do Pipeline

O código executa as seguintes transformações nos dados:

### 1. Ingestão e Normalização
- Carregamento de dados em formato JSON.
- **Flattening**: Uso de `json_normalize` para transformar objetos aninhados em colunas tabulares.
- **Explosão de Dados**: Aplicação do método `.explode()` para expandir listas (como descrições e comodidades) em múltiplas linhas, garantindo a atomicidade dos dados.

### 2. Limpeza e Tratamento (Data Cleaning)
- **Conversão de Tipos**: Transformação de strings numéricas para `int64` e `float64` (ex: número de quartos, banheiros, hóspedes).
- **Tratamento de Strings**:
  - Remoção de caracteres especiais de moeda (`$`, `,`) para conversão correta de preços.
  - Normalização de texto (lowercase) e limpeza de caracteres indesejados usando **Regex** (Expressões Regulares).
- **Tokenização**: Separação de descrições textuais em listas de palavras (tokens) para análise textual.

### 3. Engenharia de Recursos (Feature Engineering)
- **Dados Temporais**: Conversão de strings de data para objetos `datetime`.
- **Análise de Disponibilidade**: Agrupamento e contagem de vagas disponíveis por mês para análise de oferta temporal.

## 🚀 Como Executar

Para reproduzir este projeto em sua máquina local:

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/pedronkz/data-wrangling-pandas.git](https://github.com/pedronkz/data-wrangling-pandas.git)
