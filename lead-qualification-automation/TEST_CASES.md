# QA Test Cases — Automated Lead Qualification System

## Test Objective

Validate the functionality, data processing, conditional filtering, API integration, database persistence, AI-generated content, and notification behavior of the eight-step Zapier lead qualification workflow.

## Test Environment

- Automation Platform: Zapier
- Lead Capture: YouForm
- API Integration: Apollo API via Webhooks by Zapier
- Business Logic: Code by Zapier (JavaScript)
- Database: PostgreSQL
- Conditional Logic: Filter by Zapier
- AI Generation: Google Gemini
- Email Delivery: Gmail

## Test Execution Summary

| Status | Count |
|---|---:|
| Passed (supported by reported test evidence) | 2 |
| Pending / Not independently verified | 8 |
| Total documented test cases | 10 |

*Results reflect the available testing evidence, not a complete end-to-end certification.*

## Functional Test Cases

| Test ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC-001 | Submit a valid lead using YouForm | Zapier captures submitted lead information | Passed |
| TC-002 | Request company enrichment from Apollo API | Valid company information is returned | Pending verification |
| TC-003 | Calculate lead qualification score | Correct score is calculated from input data | Pending verification |
| TC-004 | Classify a high-priority lead | Lead is classified as High according to configured scoring rules | Pending verification |
| TC-005 | Save processed lead in PostgreSQL | Database record is created with correct fields | Pending verification |
| TC-006 | Filter high-priority lead | Qualifying lead continues to AI and notification steps | Pending verification |
| TC-007 | Generate AI lead summary and outreach draft | Relevant and correctly structured content is generated | Pending verification |
| TC-008 | Format notification email | Email output follows expected structure | Pending verification |
| TC-009 | Send high-priority notification via Gmail | Notification arrives with lead information and AI-generated draft | Passed |
| TC-010 | Process low-priority lead | Notification is skipped according to configured filtering rules | Not executed / pending |

## Observed Test Evidence

### YouForm Submission

A test lead submission was successfully captured by the Zapier trigger.

### High-Priority Notification

A high-priority test produced a notification email containing:

- Lead qualification score: 70
- Priority: High
- Lead summary
- Qualification reason
- AI-generated outreach draft

The notification was received through Gmail.

## Integration Issues and Limitations

### Apollo API

Authentication, permissions, and enrichment parameter issues were encountered during integration development.

A successful live enrichment response has not been independently confirmed in the available evidence.

### PostgreSQL

The database step is included in the workflow architecture.

A successful insert and independent record verification remain to be documented.

## Additional Negative Test Scenarios

The following scenarios should be executed during future testing:

- Missing or invalid email address
- Empty company name or website
- Apollo API authentication failure
- API timeout or rate limiting
- Database connection failure
- Duplicate lead submission
- Gemini response failure
- Gmail delivery failure

## Recommended Evidence

Store sanitized screenshots in the `screenshots/` directory showing:

- Workflow overview
- Successful YouForm trigger test
- Lead score and priority output
- Database record verification, when available
- Gmail high-priority notification

Do not expose API keys, credentials, or personal lead information.

## Overall QA Status

**Partially verified.**

Lead intake and Gmail notification delivery have supporting test evidence. Remaining integration, scoring accuracy, conditional routing, negative testing, and database persistence scenarios require further verification.
