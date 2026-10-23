# QA Test Cases — Asana Task Lifecycle & Client Communication Automation

## Test Objective

Validate the functionality of a multi-path Zapier automation triggered by Asana task status updates.

Testing covers conditional routing, Google Drive operations, Asana task creation, Gmail notifications, delayed follow-ups, response checks, and workflow integration.

## Test Environment

- Automation Platform: Zapier
- Trigger: Asana — Updated Task
- Conditional Routing: Paths by Zapier
- File Management: Google Drive
- Email Automation: Gmail
- Scheduling: Delay by Zapier
- Conditional Logic: Filter by Zapier

## Test Execution Summary

**Execution Result: All five configured workflow paths passed.**

| Metric | Result |
|---|---|
| Workflow paths tested | 5 |
| Paths passed | 5 |
| Paths failed | 0 |
| Path execution success rate | 100% |
| Negative and edge-case coverage | Not fully verified |

The results above reflect reported execution of the five configured workflow paths, not exhaustive testing of every possible input or failure condition.

## Functional Test Cases

| Test ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC-001 | Update an Asana task | Zapier detects the task update | Passed |
| TC-002 | Status: Ready to Start | Correct conditional path executes | Passed |
| TC-003 | Create Google Drive lead folder | Folder created successfully | Passed |
| TC-004 | Create Asana social media task | Task created successfully | Passed |
| TC-005 | Status: No Response | Correct conditional path executes | Passed |
| TC-006 | Send initial follow-up email | Gmail sends the message | Passed |
| TC-007 | Execute follow-up delay | Configured delay completes | Passed |
| TC-008 | Check client response | Gmail response check executes | Passed |
| TC-009 | Skip follow-up when response exists | Unnecessary email is not sent | Not separately verified |
| TC-010 | Send second follow-up when no response exists | Second email is sent | Passed |
| TC-011 | Status: Quoted | Correct conditional path executes | Passed |
| TC-012 | Execute quote follow-up sequence | Gmail and delay steps execute | Passed |
| TC-013 | Check quote response | Response check and filter execute | Passed |
| TC-014 | Status: Approved | Correct conditional path executes | Passed |
| TC-015 | Retrieve PDF from Google Drive | Correct PDF retrieved | Passed |
| TC-016 | Send welcome email with PDF | Gmail sends welcome email with attachment | Passed |
| TC-017 | Status: Paid and Closed | Service email is sent | Passed |
| TC-018 | Use an unsupported task status | No unrelated path executes | Not Tested |

## Path Execution Results

### Path 1 — Ready to Start

**Status: PASSED**

- Google Drive lead folder creation completed.
- Asana social media content task creation completed.

### Path 2 — No Response

**Status: PASSED**

- Initial Gmail follow-up executed.
- Delay step completed.
- Response check executed.
- Conditional filter and subsequent follow-up actions executed as configured.

### Path 3 — Quoted

**Status: PASSED**

- Quote follow-up email executed.
- Delay step completed.
- Quote response check executed.
- Conditional filter and subsequent follow-up actions executed as configured.

### Path 4 — Approved

**Status: PASSED**

- Google Drive PDF retrieval completed.
- Gmail welcome email action executed with the configured attachment.

### Path 5 — Paid and Closed

**Status: PASSED**

- Service email action executed successfully.

## Negative Test Scenarios

The following scenarios are recommended for additional testing:

| Scenario | Status |
|---|---|
| Invalid recipient email | Not Tested |
| Missing PDF attachment | Not Tested |
| Duplicate Asana task update | Not Tested |
| Gmail authentication failure | Not Tested |
| Google Drive permission failure | Not Tested |
| Unsupported task status | Not Tested |
| Client replies before second follow-up | Not separately verified |

## Test Evidence

Workflow execution was reported as successful across all five configured paths.

Supporting screenshots may include:

- Zapier execution history
- Google Drive folder creation
- Asana task creation
- Gmail follow-up messages
- Successful PDF retrieval
- Welcome and service notifications

Screenshots should use anonymized test data and exclude credentials or private client information.

## Overall QA Result

**PASS — All five configured workflow paths completed successfully during reported testing.**

Additional negative testing, duplicate prevention, and response-based suppression scenarios remain recommended before production deployment.
