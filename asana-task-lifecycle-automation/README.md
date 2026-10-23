# Asana Task Lifecycle & Client Communication Automation

### Multi-Path Workflow Automation Using Zapier, Asana, Google Drive & Gmail

A status-driven workflow automation project designed to coordinate task management, lead follow-ups, document retrieval, and client communications using Zapier.

This project demonstrates the implementation and functional testing of a multi-branch automation workflow integrating Asana, Google Drive, Gmail, Paths by Zapier, Delay by Zapier, and Filter by Zapier.

## Project Overview

This project demonstrates how an Asana task update can trigger different automated actions based on its current status.

The workflow uses five conditional paths to manage client-related activities, including folder creation, social media task creation, follow-up emails, delayed response checks, welcome messages, and service notifications.

**Primary Objective:** Reduce repetitive administrative tasks, improve workflow consistency, and standardize client communication throughout different stages of the task lifecycle.

## Workflow Architecture

![Asana Task Lifecycle Workflow](screenshots/asana-task-lifecycle-workflow.png)

The automation begins with an Asana task update and routes execution through five status-based conditional paths.

## Technology Stack

| Technology | Purpose |
|---|---|
| Asana | Task status updates and automated task creation |
| Zapier | Workflow orchestration and application integration |
| Paths by Zapier | Status-based conditional branching |
| Google Drive | Folder creation and PDF document retrieval |
| Gmail | Automated follow-up and client communication emails |
| Delay by Zapier | Scheduled follow-up intervals |
| Filter by Zapier | Conditional processing based on response checks |

## Workflow Process

### Step 1 — Asana Trigger

**Application:** Asana

**Trigger Event:** Updated Task

The workflow starts when an existing Asana task is updated.

Zapier receives the task information, including the status field used to determine which automation path should execute.

### Step 2 — Conditional Routing

**Application:** Paths by Zapier

Paths by Zapier evaluates the Asana task status and directs execution to the appropriate workflow branch.

The automation supports five task statuses:

1. Ready to Start
2. No Response
3. Quoted
4. Approved
5. Paid and Closed

## Five Workflow Paths

### Path 1 — Ready to Start

**Trigger Condition:** Task status is Ready to Start.

**Automated Actions:**

1. Google Drive — Create Lead Folder
2. Asana — Create Social Media Content Task

**Purpose:**

Automatically prepare a project workspace and initiate content-related activities when a task is ready to begin.

**Reported Test Result:** Passed

### Path 2 — No Response

**Trigger Condition:** Task status is No Response.

**Automated Actions:**

1. Gmail — Send Initial Follow-Up Email
2. Delay by Zapier — Wait Before Second Follow-Up
3. Gmail — Check If Lead Responded
4. Filter by Zapier — Evaluate No-Response Condition
5. Gmail — Send Second Follow-Up Email

**Purpose:**

Automate client follow-up activities while checking whether another message is necessary.

The workflow uses a delay and conditional filter to control subsequent email processing.

**Reported Test Result:** Passed

### Path 3 — Quoted

**Trigger Condition:** Task status is Quoted.

**Automated Actions:**

1. Gmail — Send Weekly Quote Follow-Up
2. Delay by Zapier — Wait Before Next Follow-Up
3. Gmail — Check for Quote Response
4. Filter by Zapier — Evaluate Quote Response Condition
5. Gmail — Send Additional Quote Follow-Up

**Purpose:**

Support consistent communication with clients who have received quotations but have not yet completed the next stage of the process.

**Reported Test Result:** Passed

### Path 4 — Approved

**Trigger Condition:** Task status is Approved.

**Automated Actions:**

1. Google Drive — Find PDF Attachment
2. Gmail — Send Welcome Email with PDF

**Purpose:**

Automate document retrieval and client onboarding communications following task approval.

**Reported Test Result:** Passed

### Path 5 — Paid and Closed

**Trigger Condition:** Task status is Paid and Closed.

**Automated Action:**

1. Gmail — Send Service Email

**Purpose:**

Automatically send the configured service communication after the client workflow reaches the completed status.

**Reported Test Result:** Passed

## Key Features

- Five conditional automation paths based on Asana task status
- Automated Google Drive folder creation
- Automated Asana task creation
- Multi-stage Gmail follow-up sequences
- Delayed workflow execution
- Conditional response checking and filtering
- Google Drive PDF retrieval
- Automated welcome and service emails
- Cross-application workflow orchestration
- Functional testing of configured workflow branches

## Technical Skills Demonstrated

| Category | Skills and Technologies |
|---|---|
| Workflow Automation | Zapier triggers, actions, and multi-step workflows |
| Conditional Logic | Paths by Zapier and Filter by Zapier |
| Task Management | Asana task updates and task creation |
| Application Integration | Asana, Google Drive, and Gmail |
| Scheduling | Delay by Zapier |
| Business Process Automation | Client lifecycle and follow-up management |
| Quality Assurance | Functional testing and workflow validation |
| Test Documentation | Test case design, expected results, and execution reporting |
| Technical Documentation | Workflow architecture, setup guides, and testing records |
| Version Control | Git and GitHub |

## Testing Status & Execution Results

**Overall Functional Test Result: PASS — All five configured workflow paths were reported as successfully executed during development.**

### Test Execution Summary

| Test Metric | Result |
|---|---|
| Total configured workflow paths | 5 |
| Paths reported as passed | 5 |
| Paths reported as failed | 0 |
| Reported path success rate | 100% |
| Successful Zap History runs visible | 3 |
| Observed execution date | October 15, 2026 |
| Negative and edge-case testing | Additional verification recommended |

The reported success rate applies to the five configured workflow paths tested during development. It does not represent exhaustive testing of all possible failure conditions.

### Functional Test Results

| Test ID | Workflow Path | Expected Result | Reported Status |
|---|---|---|---|
| TC-P01 | Ready to Start | Create Google Drive folder and Asana task | Passed |
| TC-P02 | No Response | Execute follow-up email, delay, response check, filter, and subsequent email actions as configured | Passed |
| TC-P03 | Quoted | Execute quote follow-up sequence and conditional processing | Passed |
| TC-P04 | Approved | Retrieve PDF and send welcome email | Passed |
| TC-P05 | Paid and Closed | Send service-related email | Passed |

### Successful Zap History Executions

Three successful Zap runs were observed in Zapier's execution history on October 15, 2026.

| Execution Time | Zap History Status |
|---|---|
| 10:42 AM | Successful |
| 10:43 AM | Successful |
| 10:54 AM | Successful |

These records demonstrate successful Zap executions.

**Evidence limitation:** The available history screenshot does not independently identify which conditional path was executed in each run. The five-path pass results are based on the reported functional testing.

### QA Validation Areas

Functional testing focused on:

- Asana task update triggering
- Status-based conditional routing
- Google Drive folder creation
- Asana task creation
- Gmail follow-up processing
- Delayed workflow execution
- Response checks and conditional filtering
- PDF retrieval
- Welcome email processing
- Service notification processing

### Additional Testing Recommendations

The following scenarios are recommended for further validation:

| Scenario | Status |
|---|---|
| Invalid or unsupported Asana task status | Not separately verified |
| Duplicate task updates | Not separately verified |
| Missing PDF attachment | Not separately verified |
| Gmail authorization failure | Not separately verified |
| Google Drive permission failure | Not separately verified |
| Client response suppresses unnecessary follow-up | Not separately verified |
| Workflow retry and error recovery | Not separately verified |

### QA Documentation

Detailed functional test cases and reported execution results are available in [TEST_CASES.md](TEST_CASES.md).

## Project Documentation

| Document | Description |
|---|---|
| [README.md](README.md) | Project overview, architecture, and testing summary |
| [SETUP.md](SETUP.md) | Technical configuration and setup instructions |
| [TEST_CASES.md](TEST_CASES.md) | Functional test cases and execution results |
| [screenshots/](screenshots/) | Workflow architecture screenshot |

## Security Considerations

- Do not publish Gmail credentials, authentication tokens, or API keys.
- Use anonymized test records in public screenshots.
- Verify email recipients before enabling automated notifications.
- Avoid publishing confidential client PDFs.
- Apply appropriate access permissions to Asana and Google Drive.
- Review automated follow-up conditions to prevent unintended messages.

## Known Limitations

- Repeated Asana task updates may require additional duplicate-execution controls.
- Automated follow-ups depend on correctly configured Gmail response matching.
- Delay execution depends on Zapier scheduling and service availability.
- Missing or inaccessible Google Drive documents may interrupt onboarding.
- Additional negative and edge-case testing is recommended before production deployment.

## Future Enhancements

- Duplicate task execution prevention
- Centralized workflow monitoring
- Automated error notifications
- Retry and recovery mechanisms
- Additional negative and regression tests
- Follow-up frequency controls
- Client communication reporting

## Project Status

**Configured and functionally tested.**

All five status-based workflow paths were reported as passing during development. Three successful Zap executions were also observed in Zap History.

The project demonstrates multi-path workflow orchestration, cross-application integrations, conditional processing, delayed follow-ups, and QA documentation.

Additional negative and failure-recovery testing is recommended before production deployment.
