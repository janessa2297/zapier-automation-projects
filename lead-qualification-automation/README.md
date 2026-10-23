# AI-Powered Lead Qualification & Scoring Automation

An eight-step sales workflow automation built with Zapier, YouForm, Apollo API, JavaScript, PostgreSQL, Google Gemini, and Gmail.

## Project Overview

This project automates lead intake, enrichment requests, qualification scoring, database processing, conditional filtering, and AI-assisted sales notifications.

## Workflow Architecture

![Lead Qualification Workflow](screenshots/lead-qualification-workflow.png)

## Technology Stack

| Technology | Purpose |
|---|---|
| YouForm | Lead capture |
| Webhooks by Zapier | Apollo API integration |
| Code by Zapier | Lead scoring and classification |
| PostgreSQL | Lead record storage |
| Filter by Zapier | High-priority lead filtering |
| Google Gemini | Lead summaries and outreach drafts |
| Formatter by Zapier | Email content formatting |
| Gmail | Sales team notifications |

## Workflow Process

1. A lead submits the YouForm qualification form.
2. Zapier requests company enrichment through the Apollo API.
3. JavaScript logic calculates a qualification score and priority.
4. The PostgreSQL step processes the lead record for storage.
5. A filter determines whether the lead qualifies for notification.
6. Gemini generates a lead summary and suggested outreach.
7. Formatter structures the email content.
8. Gmail sends the high-priority lead alert.

## Verified Testing Evidence

A high-priority test lead was classified with a score of 70, and a Gmail notification containing an AI-generated lead summary and outreach draft was received.

## Integration Limitations

Apollo API authentication and permissions issues were encountered during development. Successful live enrichment requires separate verification.

PostgreSQL record persistence should be verified through database query evidence before marking the database integration as fully tested.

## QA Testing Approach

- Form submission validation
- Lead score calculation
- Priority classification
- Filter condition testing
- AI output validation
- Gmail notification verification
- API error handling and database persistence verification

Detailed test execution results will be maintained in TEST_CASES.md.

## Security

Do not publish API keys, database credentials, private lead information, or authentication tokens.

## Future Improvements

- Retry and error handling
- Duplicate lead detection
- Database verification automation
- Low-priority lead processing
- Monitoring and alerting

## Project Status

Workflow implemented and high-priority notification demonstrated. Apollo enrichment and database persistence require additional verification.
