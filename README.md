# Titanic - Machine Learning from Disaster

Solução para o desafio [Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic) do Kaggle. 

## Pré-Processamento de Dados
O tratamento dos dados (`limpeza.ipynb`) utilizou uma abordagem direta focada em variáveis numéricas (`pclass`, `age`, `sibsp`, `parch`, `fare`):

* **Tratamento de Nulos:**
  * `Age` (Idade) e `Fare` (Tarifa) foram preenchidos com a média de suas respectivas colunas.
  * `Embarked` (Porto de Embarque) foi preenchido com o valor mais frequente (moda).
* **Limpeza de Features:** As colunas `Name`, `Ticket` e `Cabin` (alta incidência de dados faltantes) foram removidas do dataset de treinamento e testes.
* **Seleção:** Nenhuma feature nova foi criada. O treinamento foi executado isolando exclusivamente as colunas numéricas (`treino_nr`).

## Resultados dos Modelos
Três algoritmos foram testados. A Regressão Logística obteve a melhor performance e foi utilizada para a submissão final no Kaggle.

| Modelo | Score Local | Score Kaggle |
| :--- | :--- | :--- |
| **Regressão Logística** | - | **0.66746** 🏆 |
| **K-Nearest Neighbors** | 0.66480 | - |
| **Decision Tree** | 0.64245 | - |

## Estrutura do Projeto
```text
titanic_ml/
├── data/
│   ├── raw/                # Datasets originais (train.csv, test.csv)
│   ├── interim/            # Datasets limpos e tratados numéricos
│   └── reports/            # Relatórios gerados via ydata-profiling
├── notebooks/
│   ├── limpeza.ipynb           # Análise exploratória e pré-processamento
│   ├── RegressionLogis.ipynb   # Modelo Final 
│   ├── KNeighbors.ipynb        # Teste com KNN
│   └── tree_decision.ipynb     # Teste com Árvore de Decisão
├── src/                    # Scripts adicionais Python
└── requirements.txt        # Dependências do projeto

```

## Como Executar (Ambiente Linux/Fedora)

**1. Clonar o repositório**

```bash
git clone [https://github.com/pedrosantus/titanic_ml.git](https://github.com/pedrosantus/titanic_ml.git)
cd titanic_ml

```

**2. Configurar o ambiente virtual**

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

```

**3. Iniciar os notebooks**

```bash
jupyter notebook

```
