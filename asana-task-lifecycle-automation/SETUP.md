# Setup Guide — Asana Task Lifecycle & Client Communication Automation

## Project Overview

This guide explains how to configure a status-driven workflow automation using Zapier, Asana, Google Drive, Gmail, Paths by Zapier, Delay by Zapier, and Filter by Zapier.

The automation monitors Asana task updates and routes tasks through five conditional paths based on their status.

**Workflow execution status:** All five configured paths were reported as successfully tested.

## Prerequisites

Before configuring the workflow, prepare:

- A Zapier account with access to Paths, Filters, and Delay actions
- An Asana account and project containing the relevant tasks
- A Google Drive account with appropriate folder and file permissions
- A Gmail account for sending notifications
- Sample Asana tasks with test status values
- Test email recipients and sample PDF documents

Some Zapier features may require a paid subscription.

## Step 1 — Configure the Asana Trigger

**Application:** Asana

**Trigger Event:** Updated Task

1. Create a new Zap in Zapier.
2. Select Asana as the trigger application.
3. Choose the task update trigger.
4. Connect the authorized Asana account.
5. Select the relevant workspace or project, as required by the trigger.
6. Test the trigger using an updated Asana task.
7. Confirm that the output contains the task identifier, status, and other required fields.

**Expected result:** Zapier receives the updated task information.

## Step 2 — Configure Paths by Zapier

**Application:** Paths by Zapier

Create five conditional paths.

Each path should evaluate the status value received from the Asana trigger.

| Path | Status Condition |
|---|---|
| Path 1 | Ready to Start |
| Path 2 | No Response |
| Path 3 | Quoted |
| Path 4 | Approved |
| Path 5 | Paid and Closed |

Use the exact status values configured in Asana.

Verify that each path evaluates the intended field and that unrelated paths do not execute.

## Step 3 — Path 1: Ready to Start

### Action 1 — Google Drive Folder Creation

**Application:** Google Drive

**Action:** Create Folder

1. Add Google Drive to the Ready to Start path.
2. Connect the Google Drive account.
3. Select the destination parent folder.
4. Map the Asana task or lead identifier to the folder name.
5. Test folder creation.
6. Verify the folder appears in the expected location.

### Action 2 — Asana Task Creation

**Application:** Asana

**Action:** Create Task

1. Add an Asana task creation action.
2. Select the appropriate workspace and project.
3. Map the task title and other required information.
4. Configure the task for social media content preparation.
5. Test the action.
6. Verify that the task appears in Asana.

**Expected result:** A Google Drive folder and a new Asana task are created.

## Step 4 — Path 2: No Response

### Action 1 — Send Initial Follow-Up Email

**Application:** Gmail

1. Add a Gmail email action.
2. Connect the authorized Gmail account.
3. Map the intended recipient from the available task or lead information.
4. Configure the subject and follow-up message.
5. Test the email using a test recipient.

### Action 2 — Configure Delay

**Application:** Delay by Zapier

1. Add the configured delay action.
2. Specify the intended waiting interval.
3. Test or inspect the scheduled execution.
4. Confirm that the workflow resumes after the delay.

### Action 3 — Check for a Response

**Application:** Gmail

1. Add the Gmail action used to check for a matching response.
2. Configure the search or matching criteria.
3. Use the relevant sender, recipient, subject, or conversation identifiers.
4. Verify the response detection output.

### Action 4 — Apply Conditional Filter

**Application:** Filter by Zapier

1. Add a filter after the Gmail response check.
2. Configure the condition for continuing when no qualifying response exists.
3. Test the filter with representative response data.

### Action 5 — Send Second Follow-Up

**Application:** Gmail

1. Add the second follow-up email action.
2. Map the correct recipient.
3. Configure the second follow-up content.
4. Test the email.

**Expected result:** The second follow-up is sent only when the configured filter permits it.

## Step 5 — Path 3: Quoted

### Action 1 — Send Quote Follow-Up

Use Gmail to send the configured quote follow-up email.

### Action 2 — Configure Delay

Use Delay by Zapier to wait for the configured interval.

### Action 3 — Check Quote Response

Use Gmail to locate the relevant quote-related response.

### Action 4 — Apply Filter

Use Filter by Zapier to determine whether another follow-up is necessary.

### Action 5 — Send Additional Quote Follow-Up

Use Gmail to send the subsequent message when the filter condition is satisfied.

**Expected result:** Quote follow-ups execute according to the configured schedule and response conditions.

## Step 6 — Path 4: Approved

### Action 1 — Retrieve PDF Document

**Application:** Google Drive

1. Add the Google Drive file lookup action.
2. Configure the file search criteria.
3. Identify the relevant PDF document.
4. Test the lookup.
5. Verify that the correct file is returned.

### Action 2 — Send Welcome Email

**Application:** Gmail

1. Add a Gmail email action.
2. Map the intended recipient.
3. Configure the welcome message.
4. Map the PDF file output to the attachment field.
5. Test the action.
6. Verify that the received email contains the intended attachment.

**Expected result:** The approved client receives the configured welcome email and PDF.

## Step 7 — Path 5: Paid and Closed

**Application:** Gmail

1. Add the service email action.
2. Map the correct recipient.
3. Configure the service-related message.
4. Test the action.
5. Verify delivery to the intended test inbox.

**Expected result:** A service notification is sent for the Paid and Closed status.

## Step 8 — Execute and Validate the Workflow

Test each of the five statuses using representative Asana tasks.

| Path | Reported Execution Result |
|---|---|
| Ready to Start | Passed |
| No Response | Passed |
| Quoted | Passed |
| Approved | Passed |
| Paid and Closed | Passed |

All five configured paths were reported as successfully executed during development.

See [TEST_CASES.md](TEST_CASES.md) for the functional test cases and additional scenarios requiring verification.

## Troubleshooting

### Incorrect Path Execution

- Verify the Asana status field mapping.
- Confirm the exact status text.
- Review the path conditions.

### Gmail Email Not Sent

- Check Gmail authorization.
- Verify the recipient address.
- Inspect the Zap execution history.
- Review any filters preventing execution.

### Delay Does Not Resume as Expected

- Check the configured delay interval.
- Inspect Zapier task history.
- Verify the workflow has not been paused or disabled.

### PDF Attachment Missing

- Confirm the Google Drive file exists.
- Check file permissions.
- Verify that the correct file output is mapped to Gmail.

### Duplicate Notifications

- Check whether repeated Asana updates retrigger the workflow.
- Consider storing notification status or a unique task identifier to prevent duplicate sends.

## Security Considerations

- Do not publish Gmail credentials or access tokens.
- Use anonymized client and task data in screenshots.
- Verify email recipients before enabling the workflow.
- Limit connected application permissions.
- Avoid uploading private client PDFs to public repositories.

## Future Improvements

- Automated duplicate notification prevention
- Centralized workflow logging
- Error notifications and retry handling
- Additional negative test coverage
- Follow-up frequency controls
- Automated monitoring of workflow failures

## Project Status

**Configured and tested:** All five status-based workflow paths were reported as passing during development.

Additional negative, boundary, and failure recovery tests are recommended before production deployment.
