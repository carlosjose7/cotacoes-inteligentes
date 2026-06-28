# 📈 Cotações Inteligentes

Sistema em Python para atualização automática de cotações de ativos financeiros e indicadores econômicos, integrando dados de múltiplas APIs e disponibilizando-os em formato pronto para análise no Excel, Power BI ou outras ferramentas.

---

## ✨ Funcionalidades

* 📊 Atualização automática de ações americanas
* 💰 Atualização automática de ETFs
* 🪙 Atualização automática de criptomoedas
* 🇧🇷 Consulta de indicadores econômicos brasileiros

  * CDI
  * Selic
  * IPCA
* 📄 Exportação de dados para CSV
* 📈 Integração com Excel (Power Query) e Power BI

---

## 🛠️ Tecnologias

* Python 3.11+
* Requests
* Pandas
* python-dotenv
* Alpha Vantage API
* Banco Central do Brasil (SGS)

---

## 📂 Estrutura do projeto

```text
cotacoes-inteligentes/
│
├── .env                    # 🔐 Variáveis de ambiente (NÃO versionado)
├── .gitignore
├── config.py               # Leitura de variáveis do .env
├── carteira.csv            # Lista de ativos monitorados
├── cotacoes.py             # Atualização de cotações (ações + cripto)
├── indicadores.py          # Consulta de indicadores econômicos
├── cotacoes.csv            # Saída gerada (ignorado pelo git)
├── indicadores.csv         # Saída gerada (ignorado pelo git)
├── requirements.txt
└── README.md
```

---

## 🔐 Configuração de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
ALPHA_VANTAGE_API_KEY=sua_chave_aqui
```

---

## ⚙️ config.py

```python
import os
from dotenv import load_dotenv

load_dotenv()

API_KEY = os.getenv("ALPHA_VANTAGE_API_KEY")
```

---

## 📥 Instalação

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/cotacoes-inteligentes.git
cd cotacoes-inteligentes
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

---

## ▶️ Execução

Atualizar cotações:

```bash
python cotacoes.py
```

Atualizar indicadores econômicos:

```bash
python indicadores.py
```

---

## 📊 Ativos monitorados

### Ações e ETFs

MSFT, NVDA, GOOGL, AMD, AAPL, TSLA, PLTR, KO, JNJ, LLY, VOO

### Criptomoedas

BTC, BNB, ADA, DOGE, SHIB, GALA, VANRY, JASMY, COTI, IOST, WIN, SANTOS, PERL, SSV

### Indicadores econômicos

CDI, Selic, IPCA

---

## 🚀 Roadmap

* [x] Integração com Alpha Vantage
* [x] Integração com Banco Central (SGS)
* [x] Exportação CSV
* [ ] Histórico de cotações (time series)
* [ ] Dashboard em Excel automatizado
* [ ] Dashboard em Power BI
* [ ] Persistência em DuckDB ou SQLite
* [ ] Agendamento automático (cron / Task Scheduler)
* [ ] Dockerização do projeto
* [ ] API própria para consumo dos dados

---

## 🔒 Boas práticas de segurança

* Nunca versionar o arquivo `.env`
* Nunca expor API keys no código
* Rotacionar chaves em caso de exposição

---

## 👨‍💻 Autor

Desenvolvido por Carlos Silva.
