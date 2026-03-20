# SmartAgent: Multi-agent-based [S]imulation of Real-world Stock [Mar]ket [T]rading

## Introduction

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
