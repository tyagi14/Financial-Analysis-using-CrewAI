# 💹 Financial Analysis using CrewAI

A multi-agent AI system for automated financial analysis and trading strategy development, built with [CrewAI](https://github.com/joaomdmoura/crewAI).

## 🧠 Overview

This project implements a **hierarchical multi-agent collaboration system** where four specialized AI agents work together to analyze a given stock, develop trading strategies, plan trade execution, and assess associated risks — all orchestrated by a CrewAI manager LLM.

## 🏗️ Architecture

```
Manager LLM (GPT-3.5-turbo)
        │
        ├── 🔍 Data Analyst Agent        → Market data monitoring & trend analysis
        ├── 📈 Trading Strategy Agent    → Strategy development based on analysis
        ├── ⚙️  Execution Agent           → Optimal trade execution planning
        └── 🛡️  Risk Management Agent    → Risk evaluation & mitigation
```

## 🤖 Agents & Tasks

| Agent | Role | Task |
|-------|------|------|
| **Data Analyst** | Monitor & analyze real-time market data | Data Analysis Task |
| **Trading Strategy Developer** | Develop & refine trading strategies | Strategy Development Task |
| **Trade Advisor** | Suggest optimal trade execution methods | Execution Planning Task |
| **Risk Advisor** | Evaluate risks & suggest safeguards | Risk Assessment Task |

Each agent is equipped with:
- `SerperDevTool` — for web search
- `ScrapeWebsiteTool` — for web scraping

## 🔄 Workflow

The crew runs using a **Hierarchical Process**, where the manager LLM delegates tasks to the appropriate agents and synthesizes the results into a comprehensive financial report.

```
Input (stock, capital, risk tolerance, strategy preference)
        ↓
  Manager LLM delegates tasks
        ↓
  Agents collaborate & produce outputs
        ↓
  Final Report (market insights → strategies → execution plan → risk report)
```

## 🚀 Getting Started

### Prerequisites

- Python >= 3.10 and <= 3.13
- OpenAI API Key
- Serper API Key (for web search)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/financial-analysis-crewai.git
cd financial-analysis-crewai

# Install dependencies
pip install -r requirements.txt
```

### Environment Variables

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_openai_api_key_here
OPENAI_MODEL_NAME=gpt-4-turbo
SERPER_API_KEY=your_serper_api_key_here
```

> ⚠️ **Never commit your `.env` file or API keys to GitHub!**

### Running the Notebook

Open `Financial_Analysis_using_CrewAI.ipynb` in Jupyter or Google Colab and run all cells.

### Configuring the Inputs

Modify the `financial_trading_inputs` dictionary to analyze any stock:

```python
financial_trading_inputs = {
    'stock_selection': 'AAPL',          # Ticker symbol
    'initial_capital': '100000',        # Starting capital in USD
    'risk_tolerance': 'Medium',         # Low / Medium / High
    'trading_strategy_preference': 'Day Trading',  # e.g., Day Trading, Swing Trading
    'news_impact_consideration': True
}
```

## 📦 Dependencies

| Package | Purpose |
|---------|---------|
| `crewai` | Multi-agent orchestration framework |
| `crewai_tools` | Tools: SerperDev, ScrapeWebsite |
| `langchain-openai` | LLM integration (manager LLM) |
| `openai` | GPT-4 / GPT-3.5 API |
| `python-dotenv` | Environment variable management |

Install all with:

```bash
pip install -r requirements.txt
```

## 📁 Project Structure

```
financial-analysis-crewai/
│
├── Financial_Analysis_using_CrewAI.ipynb   # Main notebook
├── requirements.txt                         # Python dependencies
├── .env.example                             # Example environment variables
├── .gitignore                               # Files to exclude from Git
└── README.md                                # Project documentation
```

## ⚠️ Disclaimer

This project is for **educational purposes only**. The outputs from this system should **not** be used as actual financial or investment advice. Always consult a qualified financial advisor before making trading decisions.

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
