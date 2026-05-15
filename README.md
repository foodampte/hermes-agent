# Hermes Agent

A fork of [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) — an autonomous AI agent framework powered by Hermes models with tool-use and function-calling capabilities.

## Features

- 🤖 **Hermes Model Integration** — Optimized for NousResearch Hermes series models
- 🛠️ **Tool Use & Function Calling** — Structured JSON tool calls with automatic execution
- 🔄 **Agentic Loops** — Multi-step reasoning and task completion
- 🐳 **Docker Support** — Containerized deployment ready
- 🔌 **OpenAI-Compatible API** — Drop-in replacement for OpenAI agents

## Requirements

- Python 3.10+
- Docker (optional, for containerized deployment)
- An OpenAI-compatible API endpoint (e.g., vLLM, Ollama, LM Studio) or OpenAI API key

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/your-org/hermes-agent.git
cd hermes-agent
```

### 2. Configure environment

```bash
cp .env.example .env
# Edit .env with your settings
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the agent

```bash
python main.py
```

## Docker Deployment

```bash
docker build -t hermes-agent .
docker run --env-file .env hermes-agent
```

## Configuration

See [`.env.example`](.env.example) for all available configuration options.

Key settings:

| Variable | Description | Default |
|---|---|---|
| `OPENAI_API_BASE` | API base URL | `https://api.openai.com/v1` |
| `OPENAI_API_KEY` | API key | *(required)* |
| `MODEL_NAME` | Model to use | `NousResearch/Hermes-3-Llama-3.1-70B` |
| `MAX_ITERATIONS` | Max agent loop iterations | `10` |
| `TEMPERATURE` | Sampling temperature | `0.7` |

## Architecture

```
hermes-agent/
├── main.py              # Entry point
├── agent/
│   ├── core.py          # Agent loop and orchestration
│   ├── tools.py         # Tool definitions and registry
│   └── prompts.py       # System prompts
├── tools/
│   ├── web_search.py    # Web search tool
│   ├── code_exec.py     # Code execution tool
│   └── file_ops.py      # File operations tool
└── utils/
    ├── config.py        # Configuration management
    └── logging.py       # Logging utilities
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/my-feature`)
3. Commit your changes
4. Open a Pull Request

Please check the [issue templates](.github/ISSUE_TEMPLATE/) for bug reports and feature requests.

## License

MIT License — see [LICENSE](LICENSE) for details.

## Acknowledgements

- [NousResearch](https://github.com/NousResearch) for the original hermes-agent
- [Hermes Model Series](https://huggingface.co/NousResearch) for the underlying LLMs
