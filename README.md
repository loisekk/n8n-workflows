# n8n Workflows

A collection of production-ready n8n automation workflows — AI assistants, content tools, lead management, and more.

[![n8n](https://img.shields.io/badge/n8n-automation-blue)](https://n8n.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## Quick Start

1. Download any `.json` workflow file
2. Open n8n → **Workflows** → **Import from File**
3. Configure credentials for connected services
4. Activate the workflow

## Workflows

### AI Assistants

| Workflow | Description | Nodes | Status |
|----------|-------------|-------|--------|
| [Personal Assistant](personal-assistant/) | Telegram bot with Ollama, Postgres memory, and DuckDuckGo search | 15+ | Production |

### Content & Marketing

| Workflow | Description | Nodes | Status |
|----------|-------------|-------|--------|
| [Content Repurposer](content-repurposer/) | Transform content across platforms with AI | - | Production |
| [LinkedIn Automation](linkedin/) | Automate LinkedIn posts with AI generation | - | Production |

### Business Operations

| Workflow | Description | Nodes | Status |
|----------|-------------|-------|--------|
| [Lead Enrichment](lead-enrichment/) | Enrich and qualify leads automatically | - | Production |
| [Meeting Notes](meeting-notes/) | Automated meeting notes and summaries | - | Production |

## Tech Stack

- **n8n** — Workflow automation platform
- **Ollama** — Local LLM inference (qwen2.5:3b)
- **PostgreSQL** — Conversation memory & data storage
- **Telegram Bot API** — Messaging interface
- **DuckDuckGo** — Web search (no API key required)

## Project Structure

```
n8n-workflows/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── .gitignore
├── personal-assistant/
│   ├── README.md
│   ├── workflows/
│   │   └── personal-assistant-v3.json
│   ├── schema/
│   │   └── memory-schema.sql
│   └── config.yml
├── content-repurposer/
│   ├── README.md
│   └── workflows/
│       └── ai-content-repurposer.json
├── lead-enrichment/
│   ├── README.md
│   └── workflows/
│       └── lead-enrichment-pipeline.json
├── linkedin/
│   ├── README.md
│   └── workflows/
│       └── automate-linkedin-posts-with-ai.json
└── meeting-notes/
    ├── README.md
    └── workflows/
        └── automated-meeting-notes.json
```

## Contributing

Contributions are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

## Author

**Yash Brahmankar** — [GitHub](https://github.com/yashbrahmankar)
