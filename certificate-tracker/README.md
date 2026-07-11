# Certificate Tracker

Automated workflow to track free certifications from top tech companies.

## Free Certifications to Pursue

### Tier 1 - High Value (Proctored Exams)

| Certification | Provider | Cost | Exam Format | Career Value |
|--------------|----------|------|-------------|--------------|
| OCI Foundations (1Z0-1085) | Oracle | **FREE** | MCQ, proctored | High |
| Professional ML Engineer | Google | $200 | 50-60 Q, 120 min | High |
| AZ-900 Azure Fundamentals | Microsoft | $165 (free vouchers available) | MCQ | High |
| Claude Certified Architect | Anthropic | $99 | 60 MCQ, 120 min | High |
| GenAI with LLMs Associate | NVIDIA | $125-400 | Proctored | Medium-High |

### Tier 2 - Free Completion Badges

| Platform | Free Courses | Certificates | Best For |
|----------|--------------|--------------|----------|
| LinkedIn Learning | 470+ hours | Yes | Soft skills, AI basics |
| Google Skills Boost | Many paths | Skill Badges | Beginners |
| Cisco Networking Academy | 30+ courses | Badges | Cybersecurity, Networking |
| IBM SkillsBuild | 1000+ courses | Digital Badges | AI, Cloud, Data Science |
| Anthropic Academy | 13 courses | Completion | Claude, AI Fluency |
| OpenAI Academy | 15+ courses | TBD mid-2026 | ChatGPT workflows |
| Microsoft Learn | 3200+ courses | Applied Skills | Azure, AI |

## Setup Instructions

### 1. Create Notion Database

Create a database with these columns:

| Column | Type | Description |
|--------|------|-------------|
| Certificate Name | Title | Name of the certification |
| Provider | Select | Google, Microsoft, Cisco, etc. |
| Status | Select | Not Started, In Progress, Completed |
| Deadline | Date | Exam/completion deadline |
| URL | URL | Link to the course |
| Notes | Text | Additional notes |

### 2. Get Notion API Key

1. Go to https://www.notion.so/my-integrations
2. Create a new integration
3. Copy the API key
4. Share your database with the integration

### 3. Get Telegram Bot Token

1. Message @BotFather on Telegram
2. Send `/newbot`
3. Copy the bot token
4. Get your chat ID from @userinfobot

### 4. Import Workflow

1. Open n8n → Workflows → Import from File
2. Select `certificate-tracker.json`
3. Update placeholder credentials
4. Activate workflow

## Features

- **Daily Reports**: Get Telegram alerts at 9 AM
- **Deadline Tracking**: Urgent alerts for certs due in 7 days
- **Progress Updates**: Webhook to update status from mobile
- **Free Resources**: Curated list of best free certificates

## API Endpoint

Update certificate status via webhook:

```bash
curl -X POST http://localhost:5678/webhook/certificate-update \
  -H "Content-Type: application/json" \
  -d '{
    "pageId": "your-notion-page-id",
    "status": "Completed",
    "notes": "Passed with 95%"
  }'
```

## Recommended Learning Path

1. **Week 1-2**: Oracle OCI Foundations (FREE exam)
2. **Week 3-4**: LinkedIn Learning - Career Essentials in Generative AI
3. **Week 5-6**: Google Skills Boost - AI Essentials
4. **Week 7-8**: Cisco Networking Academy - Introduction to Cybersecurity
5. **Week 9-10**: Microsoft Learn - AZ-900 Azure Fundamentals
6. **Week 11-12**: Anthropic Academy - AI Fluency Framework

## Resources

- [450+ Free Google Certifications](https://grow.google/certificates)
- [LinkedIn Learning Free Courses](https://www.linkedin.com/learning/)
- [Cisco Networking Academy](https://www.netacad.com/)
- [IBM SkillsBuild](https://skillsbuild.org/)
- [Oracle OCI Foundations](https://education.oracle.com/oracle-cloud-infrastructure-2024-foundations/pexam_1Z0-1085-24)
- [Microsoft Learn](https://learn.microsoft.com/)
- [Anthropic Academy](https://www.anthropic.com/academy)
- [NVIDIA DLI](https://www.nvidia.com/en-us/training/)
