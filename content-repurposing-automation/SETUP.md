# Setup Guide — AI Content Repurposing Automation

## Overview

This guide explains how to recreate the AI-powered content repurposing workflow using Zapier, Google Gemini, Google Drive, and Google Sheets.

## Prerequisites

- Zapier account with access to the required multi-step workflow features
- Google account
- Google Drive
- Google Sheets
- Google Gemini integration available in Zapier
- Sample audio or video file for testing

**Note:** Zapier plan requirements, task limits, and AI integration availability may vary.

## Step 1 — Prepare Google Drive

1. Open Google Drive.
2. Create a folder named `Content Repurposing Input`.
3. Upload a sample audio or video file.
4. Connect Google Drive to Zapier.
5. Configure the trigger: `New File in Folder`.
6. Select the input folder.
7. Test the trigger.

## Step 2 — Extract the Transcript

1. Add an `AI by Zapier` extraction step.
2. Map the uploaded media file from Google Drive.
3. Configure transcript extraction.
4. Test the step and inspect its output.

## Step 3 — Generate Blog Content

1. Add Google Gemini to generate Blog Post 1.
2. Map the extracted transcript into the prompt.
3. Request a structured response containing a title and blog body.
4. Use Formatter by Zapier to separate the title and body.
5. Repeat for Blog Post 2 using a different content angle.

## Step 4 — Generate Social Media Content

Configure four AI generation actions:

1. Instagram Post 1
2. LinkedIn Post 1
3. Instagram Post 2
4. LinkedIn Post 2

Use platform-specific prompts and map the appropriate source content.

## Step 5 — Configure Validation and Routing

1. Add Filter by Zapier.
2. Define the content validation conditions.
3. Add Paths by Zapier.
4. Configure Path A for faith-based content.
5. Configure Path B for general content.
6. Verify that the path conditions behave as intended.

## Step 6 — Configure Google Sheets

1. Create a spreadsheet named `Content Repurposing Log`.
2. Add columns for source information, transcripts, generated content, category, and status.
3. Connect Google Sheets to Zapier.
4. Map generated outputs to their corresponding columns.
5. Test row creation and verify the saved values.

## Step 7 — Test the Workflow

1. Upload a sample media file.
2. Verify the Google Drive trigger.
3. Inspect the transcript.
4. Validate both generated blog posts.
5. Validate the four social media outputs.
6. Verify Formatter results.
7. Check Filter and Path execution.
8. Confirm that Google Sheets contains the expected values.

See [TEST_CASES.md](TEST_CASES.md) for test scenarios and execution status.

## Security Considerations

- Do not commit API keys, access tokens, or credentials.
- Use test data instead of confidential production content.
- Remove private information from screenshots.
- Restrict access to connected Google accounts and spreadsheets.
- Review permissions before sharing workflow demonstrations.

## Known Limitations

- AI-generated content may require human review.
- Execution depends on Zapier and connected service availability.
- API usage and plan restrictions may affect processing.
- Negative testing and failure recovery validation remain pending.
- Social media content is generated and logged, not automatically published.

## Future Enhancements

- Add error notifications
- Add retry and failure-handling mechanisms
- Implement duplicate-file detection
- Introduce human approval before publishing
- Expand automated test coverage
