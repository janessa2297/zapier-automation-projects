# Setup Guide — AI-Powered Lead Qualification Automation

## Overview

This guide describes how to recreate an eight-step lead qualification workflow using Zapier, YouForm, Apollo API, JavaScript, PostgreSQL, Google Gemini, and Gmail.

The workflow is designed to capture leads, request company enrichment, calculate qualification scores, store lead information, and generate notifications for high-priority leads.

## Prerequisites

- Zapier account with access to the required integrations and features
- YouForm account
- Apollo account with appropriate API access
- PostgreSQL database accessible to Zapier
- Google Gemini integration
- Gmail account
- Sample lead data for testing

**Note:** Some integrations and actions may require paid plans or additional permissions.

## Step 1 — Configure YouForm

1. Create a lead capture form in YouForm.
2. Add the required fields:
   - First Name
   - Last Name
   - Email Address
   - Company Name
   - Company Size
   - Company Website
   - Lead Source
3. Publish the form.
4. Add YouForm as the Zapier trigger.
5. Select the appropriate form.
6. Submit sample data and test the trigger.

**Expected result:** Zapier receives the submitted lead fields.

## Step 2 — Configure Apollo API Integration

1. Add Webhooks by Zapier.
2. Select the appropriate HTTP request action.
3. Configure the Apollo organization enrichment endpoint according to the current API documentation.
4. Add the required authentication method.
5. Map company name, website, or domain from the YouForm submission.
6. Test the API request.
7. Inspect the HTTP response and returned company information.

**Important:** Apollo API authentication and permission limitations were encountered during development. Do not assume enrichment is successful until a valid response has been verified.

Never expose API keys in GitHub documentation or screenshots.

## Step 3 — Configure Lead Scoring

1. Add Code by Zapier.
2. Select JavaScript.
3. Map the required lead fields into the code step.
4. Implement qualification rules based on the configured business criteria.
5. Calculate a numerical lead score.
6. Assign a priority classification.
7. Return the score and priority as structured output fields.

**Observed example:**

- Lead Score: 70
- Priority: High

The exact scoring thresholds and weights should match the implemented JavaScript logic.

## Step 4 — Configure PostgreSQL

1. Add PostgreSQL as an action.
2. Connect the database using authorized credentials.
3. Select the intended table and insert action.
4. Map lead information, qualification score, and priority to the corresponding columns.
5. Test the database operation.
6. Verify that the expected record exists in PostgreSQL.

**Verification requirement:** A successful Zapier action alone is not sufficient evidence of correct database persistence. Confirm the stored values using a database query.

## Step 5 — Configure High-Priority Filtering

1. Add Filter by Zapier.
2. Select the priority output from the JavaScript scoring step.
3. Configure the filter condition for high-priority leads.
4. Test the filter using a qualifying lead.
5. Verify that non-qualifying leads do not proceed to the notification actions.

## Step 6 — Configure Google Gemini

1. Add a Google Gemini content generation action.
2. Map the lead information and available company details.
3. Provide instructions to generate:
   - Lead summary
   - Qualification reason
   - Recommended outreach message
4. Test the AI output.
5. Review the response for accuracy and relevance.

AI-generated statements should not invent company information or unsupported qualification details.

## Step 7 — Configure Formatter

1. Add Formatter by Zapier.
2. Select the required text processing action.
3. Map the Gemini output.
4. Format the content for the notification email.
5. Verify that the final message contains the intended sections.

## Step 8 — Configure Gmail Notification

1. Add Gmail as the final action.
2. Select the email sending action.
3. Connect the authorized Gmail account.
4. Configure the sales notification recipient.
5. Map lead information, qualification score, priority, and AI-generated content.
6. Test the notification.

**Expected result:** A high-priority lead generates a notification containing the lead details and suggested outreach.

## Testing

Validate the workflow using sample leads and inspect the execution history.

Recommended checks include:

- Successful form submission
- Correct lead field mapping
- API request and response validation
- Lead scoring accuracy
- PostgreSQL record persistence
- Filter behavior
- AI-generated content quality
- Email formatting and delivery

See [TEST_CASES.md](TEST_CASES.md) for detailed test cases and their recorded status.

## Known Limitations

- Apollo enrichment requires valid API permissions and authentication.
- Database persistence requires separate record verification.
- Negative and failure recovery scenarios are not fully validated.
- AI-generated content should be reviewed before use in customer outreach.
- Workflow execution depends on connected service availability and Zapier plan limits.

## Security Considerations

- Never commit API keys or database passwords.
- Use sample or anonymized lead information.
- Remove personal information from screenshots.
- Apply least-privilege access to integrations.
- Keep production credentials outside the repository.

## Future Enhancements

- Duplicate lead detection
- Error handling and retry logic
- Automated database validation
- CRM integration
- Lead scoring analytics
- Monitoring and failure notifications
