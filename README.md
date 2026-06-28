# 📈 Cotações Inteligentes

Sistema em Python para atualização automática de cotações de ativos financeiros e indicadores econômicos, integrando dados de mercado global (ações e criptomoedas) e macroeconomia brasileira, com exportação para análise em Excel e Power BI.

---

## ✨ Funcionalidades

### 📊 Mercado financeiro

* Ações americanas (Alpha Vantage)
* ETFs (ex: VOO)
* Criptomoedas (BTC, ADA, DOGE etc.)
* Variação diária e preço atual

### 🇧🇷 Indicadores macroeconômicos

* CDI atual
* Selic (meta)
* IPCA acumulado
* USD/BRL (câmbio dólar)

### 📁 Exportação

* Geração automática de CSV
* Integração com Excel (Power Query)
* Compatível com Power BI

---

## 🛠️ Tecnologias

* Python 3.11+
* Pandas
* Requests
* Alpha Vantage API
* Banco Central do Brasil (SGS)

---

## 📂 Estrutura do projeto

```text id="proj1"
cotacoes-inteligentes/
│
├── config.py              # API Key (Alpha Vantage via .env recomendado)
├── carteira.csv           # Lista de ativos monitorados
├── cotacoes.py            # Pipeline de ações + criptomoedas
├── indicadores.py         # Pipeline de indicadores macroeconômicos
├── cotacoes.csv           # Saída de mercado (gerado)
├── indicadores.csv        # Saída macro (gerado)
├── requirements.txt
├── .env                   # 🔐 variáveis sensíveis (NÃO versionado)
└── README.md
```

---

## 🔐 Configuração

Crie um arquivo `.env` na raiz do projeto:

```env id="env1"
ALPHA_VANTAGE_API_KEY=sua_chave_aqui
```

E no `config.py`:

```python id="cfg1"
import os
from dotenv import load_dotenv

load_dotenv()

API_KEY = os.getenv("ALPHA_VANTAGE_API_KEY")
```

---

## 📥 Instalação

```bash id="install1"
git clone https://github.com/seu-usuario/cotacoes-inteligentes.git
cd cotacoes-inteligentes
pip install -r requirements.txt
```

---

## ▶️ Execução

### Atualizar cotações (ações + cripto)

```bash id="run1"
python cotacoes.py
```

### Atualizar indicadores econômicos

```bash id="run2"
python indicadores.py
```

---

## 📊 Saídas geradas

### 📈 `cotacoes.csv`

Contém:

| Ativo | Preço | Variação | Variação % |
| ----- | ----: | -------: | ---------: |
| MSFT  |   ... |      ... |        ... |
| BTC   |   ... |          |            |

---

### 📉 `indicadores.csv`

Contém:

| Indicador       | Valor |
| --------------- | ----: |
| CDI Atual (%)   |   ... |
| Selic Atual (%) |   ... |
| IPCA Atual (%)  |   ... |
| USD/BRL (Dólar) |   ... |

---

## 🧠 Arquitetura do projeto

O sistema está dividido em dois pipelines:

### 1. Market Data Pipeline

* Ações via Alpha Vantage
* Criptomoedas via Alpha Vantage
* Normalização em DataFrame

### 2. Macro Data Pipeline

* Dados via Banco Central do Brasil (SGS)
* Indicadores econômicos
* Câmbio USD/BRL

---

## 🚀 Roadmap

* [x] Integração com ações e cripto
* [x] Indicadores econômicos (CDI, Selic, IPCA)
* [x] USD/BRL integrado
* [ ] Histórico de cotações (time series)
* [ ] Banco de dados (DuckDB / SQLite)
* [ ] Dashboard em Excel automatizado
* [ ] Dashboard em Power BI
* [ ] Agendamento automático (cron / Task Scheduler)
* [ ] API própria para consumo dos dados
* [ ] Dockerização do projeto

---

## 🔒 Boas práticas

* Nunca versionar `.env`
* Nunca expor API keys no código
* Respeitar rate limit da Alpha Vantage (sleep de 12s)
* Validar respostas de API antes de uso

---

## 👨‍💻 Autor

Desenvolvido por Carlos Silva.
