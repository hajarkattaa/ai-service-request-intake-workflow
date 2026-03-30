# AI Service Request Intake Workflow

## Overview

This project demonstrates an AI-powered workflow built with n8n that processes unstructured customer service requests and converts them into structured operational data.

---

## Problem

Customer service requests are often unstructured and incomplete, making it difficult to:

- extract key information
- validate completeness
- route requests efficiently

---

## Solution

This workflow:

1. Receives requests via webhook (API)
2. Uses AI (OpenAI) to extract structured data
3. Parses and validates the result
4. Routes requests based on completeness
5. Stores valid requests in Google Sheets
6. Simulates customer communication (WhatsApp)

---

## Workflow

Webhook → AI Processing → Parse & Structure Data → IF → Confirmation / Clarification → Google Sheets

---

## Example Input

Hi, I need a house cleaner tomorrow at 3 PM in Dubai Marina for 4 hours

---

## Example Output

```json
{
  "service_type": "house cleaning",
  "requested_date": "tomorrow",
  "requested_time": "3 PM",
  "location": "Dubai Marina",
  "duration": "4 hours",
  "urgency": "high",
  "completeness": "complete",
  "status": "ready_for_review"
}
```

---

## Tech Stack

- n8n (workflow automation)
- OpenAI API (AI processing)
- Google Sheets (data storage)
- Webhook (API input)


---

## Security Note

This repository does NOT include any:

- API keys
- OAuth client secrets
- tokens or credentials

You must configure your own credentials to run this workflow.

---

## Setup Requirements

To run this project, you need:

- OpenAI API key
- Google Sheets OAuth credentials
- n8n installed locally

---

## How to Use

1. Start n8n:

    npx n8n

2.Import `Workflow_webhook.json`

3.Configure:

-OpenAI credentials
-Google Sheets credentials

4.Send a request:

```bash

    curl -X POST http://localhost:5678/webhook-test/service-request \
    -H "Content-Type: application/json" \
    -d '{"raw_request":"Your request"}'

```

---

## Future Improvements

- Real WhatsApp API integration
- Email notifications
- Dashboard / analytics
- Multi-step AI conversations

---

## Notes

WhatsApp communication is simulated in this version.
It can be replaced with real API integrations (Twilio / WhatsApp Cloud API).

---

## Author

Built as part of an AI + automation learning project
