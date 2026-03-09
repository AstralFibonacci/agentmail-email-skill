---
name: agentmail-email-skill
description: Send and receive emails autonomously via AgentMail using Composio. Use when an agent needs to send outreach emails, read an inbox, or react to incoming messages.
tags: [agentmail, email, outreach, automation, composio]
---

# AgentMail Email Skill

## Purpose

Give agents the ability to send and receive emails through AgentMail inboxes via the Composio SDK.

---

## Setup

```bash
pip install composio
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

- Autonomous outreach agents (sales, partnerships, hiring)
- Inbound email monitoring and triage
- Lead follow-up sequences
- Notification delivery from agent workflows

---

## Security

- Store `AGENT_MAIL_API_KEY` in environment variables
- Never hardcode credentials or inbox addresses in shared skill files
