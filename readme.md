# SmartAgent: Multi-agent-based [S]imulation of Real-world Stock [Mar]ket [T]rading

## Introduction
Please see the [report](SmartAgent_Report.pdf) to get to know this project.

This diagram illustrates how a trading agent makes its own trading decisions.
![Figure 1. Information sources in making decisios](figure/figure1_decision.png#pic_center=60%)

And the entire trading simulation process includes three modules: Investment Module, Transaction Module, and BBS Module.

### Investment Module
The Investment Module is designed to simulate heterogeneous investor behavior in financial markets. It incorporates key functions such as interest repayment, bankruptcy checks, and loan decision-making. Each AI agent is initialized with randomized capital ranging from 100,000 to 5 million units and is assigned one of four trading profiles: conservative, aggressive, balanced, or growth-oriented. The module enforces realistic market constraints, including variable interest rates (2.7%–3.3%) and mandatory bankruptcy procedures when cash balances become negative.

A central innovation lies in the LLM-driven decision core: leveraging models such as GPT or Gemini, agents integrate real-time market data, financial reports, and online discussions to generate structured, JSON-formatted trading decisions.

### Transaction Module
At the beginning of each session, agent execution order is randomized via a stochastic scheduling mechanism, mitigating artificial deadlocks common in conventional simulations. Agents submit orders to a limit order book implemented using optimized dictionary-based data structures, enabling O(1) trade matching complexity.

Two key design principles are enforced: (1) prices are updated strictly based on the last executed trades, and (2) realistic transaction costs, including stamp duties and tiered commissions, are incorporated. The overall workflow follows a structured pipeline: random sequencing → order processing → price updating → position reconciliation. This design collectively forms a computational representation of market microstructure.

### BBS Module
The BBS Module captures the social dimension of the market. After each trading session, agents generate natural language analyses (e.g., expectations of increased volatility due to supply chain disruptions). These anonymized posts are archived and made accessible to all agents in the subsequent session, forming an information diffusion network.

This mechanism directly influences next-day decision-making: agents integrate both market data and aggregated social sentiment to produce structured outputs, enabling the modeling of socially informed trading behavior.

## Setup

1. install requirements：

```bash
pip install -r requirements.txt
```

2. Set up LLM model APIs such as openai API, gemini API or deepseek API, etc. in the util file.(The given API is not available)
3. Set up basic model settings such as the number of traders, basic time, etc. in the util file

## Run

```
python main.py --model {your model}
```

By default, the openai gpt-3.5-turbo-ca model is used.
