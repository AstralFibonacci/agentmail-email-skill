# AgentMail Ops — Claude Agent Skill

Send and receive emails programmatically via AgentMail using Composio. Designed for Claude agents that need autonomous email operations.

---

## What This Skill Does

- Send emails from agent-controlled inboxes
- Read and list incoming messages
- Retrieve specific messages by ID
- Integrate into automated outreach and notification workflows

---

## Requirements

- AgentMail API key (`AGENT_MAIL_API_KEY`)
- Composio SDK
- An AgentMail inbox (create at [agentmail.to](https://agentmail.to))

---

## Setup

```bash
pip install composio
```

Set your environment variable:

```bash
export AGENT_MAIL_API_KEY=your_key_here
```

---

## Sending Emails

```python
from composio import Composio

composio = Composio()

result = composio.tools.execute(
    slug="AGENT_MAIL_SEND_EMAIL",
    version="20260227_00",
    user_id="YOUR_COMPOSIO_USER_ID",
    arguments={
        "inbox_id": "your_inbox@agentmail.to",
        "to": ["recipient@example.com"],
        "subject": "Your Subject",
        "text": "Email body text"
    }
)
```

---

## Reading Emails

### List Messages

```python
result = composio.tools.execute(
    slug="AGENT_MAIL_LIST_MESSAGES",
    version="20260227_00",
    user_id="YOUR_COMPOSIO_USER_ID",
    arguments={
        "inbox_id": "your_inbox@agentmail.to",
        "limit": 10
    }
)
```

### Get a Specific Message

```python
result = composio.tools.execute(
    slug="AGENT_MAIL_GET_MESSAGE",
    version="20260227_00",
    user_id="YOUR_COMPOSIO_USER_ID",
    arguments={
        "inbox_id": "your_inbox@agentmail.to",
        "message_id": "<message-id-from-list>"
    }
)
```

---

## Use Cases

- Autonomous outreach agents
- Lead follow-up automation
- Notification systems
- Inbound email monitoring and response

---

## Security

- Store `AGENT_MAIL_API_KEY` in environment variables
- Never hardcode credentials in agent prompts or skill files
