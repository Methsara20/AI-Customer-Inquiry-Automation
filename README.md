# AI-Powered Customer Inquiry Automation

**n8n · Groq AI · JavaScript · Google Sheets · PostgreSQL · Gmail**

An AI-assisted workflow for customer inquiry intake, validation, deduplication, classification, priority routing, and support-team notification. Built as a hands-on automation project and tested using sample inquiries.

> **Project status:** Developed and tested. This public repository is a portfolio demonstration; it is not a claim of a verified production deployment or measured business savings.

## Problem

Manually reviewing incoming customer messages, identifying urgency, and notifying the appropriate support staff can be repetitive and inconsistent. This workflow explores how AI-assisted triage can support faster, more organized processing while keeping human review in the loop.

## How it works

1. A new inquiry arrives through a Google Sheets trigger (fed by a customer inquiry form).
2. JavaScript validation checks required fields and email formatting, and generates an inquiry identifier.
3. A lookup checks whether the inquiry has already been processed to reduce duplicate handling.
4. A Groq-powered AI agent assigns a category (`ORDER`, `DELIVERY`, `RETURN`, `COMPLAINT`, or `GENERAL`), priority (`HIGH`, `MEDIUM`, or `LOW`), a summary, and a suggested reply.
5. Structured data is mapped and stored in a PostgreSQL-backed n8n data store.
6. Gmail sends a priority-based notification to the support team.
7. The inquiry is marked **Pending Review**. Customer-facing messages are not automatically sent by this published workflow.

## Workflow overview

```text
Customer Inquiry Form / Google Sheets
                  |
         Validate & Normalize
                  |
          Duplicate Check
                  |
           Groq AI Agent
                  |
       Parse Structured Output
                  |
        Save Inquiry Record
                  |
       Priority-Based Routing
         /        |        \
      HIGH      MEDIUM      LOW
         \        |        /
       Support Team Notifications
                  |
             Pending Review
```

## Key capabilities

- Required-field and email-format validation
- Unique inquiry identifiers and duplicate detection
- AI-powered inquiry categorization and urgency triage
- Suggested replies drafted for human review (not sent automatically)
- Structured inquiry storage and processing status
- Priority-specific email notifications
- Retry settings and testing for common failure cases

## Tech stack

| Technology | Purpose |
| --- | --- |
| n8n | Workflow orchestration |
| Groq AI | AI-powered classification, summarization and draft suggestions |
| JavaScript | Data validation and output mapping |
| Google Sheets | Inquiry source / trigger |
| PostgreSQL-backed n8n storage | Structured inquiry records |
| Gmail | Support-team email notifications |

## Screenshots

Add sanitized screenshots to `screenshots/` and reference them here once available. Suggested files:

- `screenshots/workflow-overview.png`
- `screenshots/sample-ai-classification.png`
- `screenshots/sample-notification.png`

Do not publish raw execution history or screenshots containing customer data, credentials, internal addresses, or private URLs.

## Demo and sample data

Example fictional inquiries are included in `sample-data/sample-inquiries.csv`. Illustrative structured output is in `sample-data/example-ai-output.json`. These are examples, **not actual execution logs**.

## Setup / reproduction

See [Setup guide](docs/setup-guide.md). A sanitized n8n workflow export can be added to `workflow/customer-inquiry-workflow.json` once reviewed for public release. This repository does not include API credentials or live service connections.

## Testing and results

The project was tested with sample inquiries across multiple categories and priority levels. During testing, duplicate notifications and field-mapping issues were investigated and corrected. The workflow demonstrates AI-assisted triage and team notifications; **production-scale performance, time savings, and cost savings have not been measured**.

## My contribution

Designed the workflow, implemented JavaScript-based validation and output mapping, configured AI classification and email notifications, added duplicate checks, and tested/debugged the process.

## Privacy and security

All examples in this repository should use fictional data. Live credentials, customer records, internal company information and webhook URLs must never be committed. See [Security checklist](docs/security-checklist.md).

## Limitations / next steps

- Human agent review and customer reply approval workflow can be added in a future version.
- A monitoring dashboard and production metrics (time saved, error rate and notification delivery rate) can be implemented and validated separately.
- Production use would require security review, monitoring, access control and data retention policies.

## Author

**Methsara Dimalsha** · [GitHub](https://github.com/Methsara20)
