# Personal Assistant - n8n Setup Guide

## Architecture

```
Channels (WhatsApp/Telegram/Gmail)
    ↓
Gateway Normalizer → Memory Store (Postgres) → Ollama LLM
    ↓                           ↓                    ↓
Task Executor            Memory Fetch         Response Parser
    ↓                                               ↓
Scheduled Jobs                              Tool Router → Web Search
                                                    ↓
                                            Respond to Channel
```

## Prerequisites

1. **n8n** running (Docker or desktop)
2. **Ollama** installed with models pulled
3. **Postgres** database for memory
4. **API credentials** for channels

## Quick Setup

### 1. Start Ollama and pull model
```bash
ollama pull llama3
ollama serve  # runs on localhost:11434
```

### 2. Setup Postgres memory database
```bash
psql -U postgres -f memory-schema.sql
```

### 3. Import workflow into n8n
- Open n8n UI
- Click "Import from File"
- Select `personal-assistant-n8n.json`

### 4. Configure credentials in n8n

| Credential | Where to get it |
|------------|-----------------|
| **Telegram Bot** | @BotFather → /newbot → copy token |
| **Gmail OAuth2** | Google Cloud Console → APIs → Credentials |
| **Postgres** | Your Postgres connection details |

### 5. Update placeholder IDs
Replace these in the workflow:
- `YOUR_GMAIL_CREDENTIAL_ID`
- `YOUR_TELEGRAM_CREDENTIAL_ID`
- `YOUR_POSTGRES_CREDENTIAL_ID`

### 6. Set webhook URLs
- **WhatsApp**: Use WhatsApp Business API or a bridge like whatsapp-web.js
- **Telegram**: Set webhook to `https://your-n8n.com/webhook/telegram`
- **Gmail**: Polling is built-in (every minute)

## Channel Setup

### Telegram (Easiest)
1. Message @BotFather on Telegram
2. Send `/newbot` and follow prompts
3. Copy the bot token
4. Add to n8n Telegram credentials
5. Set webhook URL in BotFather

### WhatsApp
Option A: WhatsApp Business API (requires Meta approval)
Option B: Use whatsapp-web.js bridge (self-hosted)
Option C: Use Twilio WhatsApp API

### Gmail
1. Go to Google Cloud Console
2. Create OAuth2 credentials
3. Enable Gmail API
4. Add credentials in n8n

## Customization

### Change Ollama model
Edit the "Ollama LLM" node, change `model` field:
- `llama3` (default, good balance)
- `mistral` (faster)
- `codellama` (code-focused)
- `phi3` (smaller, faster)

### Add more tools
Edit the "Response Parser" node to add patterns:
```javascript
'new_tool': /your pattern (.+)/i
```

### Adjust memory window
Edit "Memory Fetch" query, change `LIMIT 20` to desired count.

## Running

1. Activate the workflow in n8n
2. Send a message to your Telegram bot
3. The assistant responds via Ollama

## Troubleshooting

| Issue | Fix |
|-------|-----|
| Ollama not responding | Ensure `ollama serve` is running |
| No Telegram response | Check bot token and webhook |
| Memory not working | Verify Postgres credentials |
| Slow responses | Try smaller model like `phi3` |
