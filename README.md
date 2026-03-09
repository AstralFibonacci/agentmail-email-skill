# agentmail-email-skill

An agent skill for sending and receiving emails autonomously via [AgentMail](https://agentmail.to). Compatible with Claude Code, OpenClaw, and any agent framework that supports skill files.

## What it does

- Send emails from agent-controlled inboxes
- List and read incoming messages
- Retrieve specific messages by ID
- Power autonomous outreach, follow-up, and notification pipelines

## When to use this skill

- An agent needs to send outreach or follow-up emails without human intervention
- You want to monitor an inbox and react to incoming messages
- You're building email-in-the-loop automation workflows

## Requirements

| Requirement | Details |
|-------------|---------|
| AgentMail account | [agentmail.to](https://agentmail.to) |
| API key | `AGENT_MAIL_API_KEY` env var |
| Composio SDK | `pip install composio` |

## Structure

```
agentmail-email-skill/
├── README.md     ← you are here (overview)
└── SKILL.md      ← full implementation guide for agents
```

## Quick example

```python
from composio import Composio

composio = Composio()

composio.tools.execute(
    slug="AGENT_MAIL_SEND_EMAIL",
    version="20260227_00",
    user_id="YOUR_COMPOSIO_USER_ID",
    arguments={
        "inbox_id": "your_inbox@agentmail.to",
        "to": ["recipient@example.com"],
        "subject": "Subject line",
        "text": "Email body"
    }
)
```

See [`SKILL.md`](./SKILL.md) for the full implementation guide.

## Tags

`ai-agent` `email` `agentmail` `automation` `outreach` `claude` `openclaw` `agent-skill` `crm` `sales-automation`
