# QA Test Cases — AI Content Repurposing Automation

## Test Objective

Validate that the Zapier automation correctly detects uploaded media, extracts transcripts, generates AI content, processes output fields, evaluates conditional paths, and logs generated content into Google Sheets.

## Test Environment

| Component | Technology |
|---|---|
| Automation Platform | Zapier |
| File Source | Google Drive |
| Transcript Extraction | AI by Zapier |
| AI Generation | Google Gemini |
| Data Transformation | Formatter by Zapier |
| Workflow Logic | Filters and Paths by Zapier |
| Output Storage | Google Sheets |

## Functional Test Cases

| Test ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC-001 | Upload a supported audio/video file | Zapier detects the new file | PASS |
| TC-002 | Extract transcript from uploaded media | Transcript is successfully extracted | PASS |
| TC-003 | Generate Blog Post 1 | Gemini generates primary blog content | PASS |
| TC-004 | Parse Blog Post 1 | Title and body are separated correctly | PASS |
| TC-005 | Generate Blog Post 2 | Gemini generates an alternative blog | PASS |
| TC-006 | Parse Blog Post 2 | Title and body are separated correctly | PASS |
| TC-007 | Generate Instagram captions | Two captions are generated | PASS |
| TC-008 | Generate LinkedIn posts | Two LinkedIn posts are generated | PASS |
| TC-009 | Validate content using Zapier Filter | Filter evaluates the configured conditions correctly | PASS |
| TC-010 | Process faith-based content | Faith-Based Path executes when its conditions match | PASS |
| TC-011 | Process general content | General Content Path executes when its conditions match | PASS |
| TC-012 | Save output in Google Sheets | Generated content is mapped to the expected columns | PASS |

## Negative Test Scenarios

| Test ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC-013 | Upload unsupported file type | Workflow follows defined handling behavior | Not Run |
| TC-014 | Process empty transcript | Workflow prevents or flags invalid content | Not Run |
| TC-015 | AI returns incomplete content | Incomplete content is detected according to validation rules | Not Run |
| TC-016 | Google Sheets connection fails | Failure is visible in Zapier execution history | Not Run |

## Test Execution Guidelines

1. Prepare a sample media file containing non-confidential content.
2. Upload the file to the monitored Google Drive folder.
3. Inspect the Zapier execution history.
4. Verify transcript and AI generation outputs.
5. Check Formatter field values.
6. Confirm Filter and Path evaluation.
7. Verify Google Sheets output against the source execution.
8. Update each test case status to Pass, Fail, or Blocked.

## Acceptance Criteria

The end-to-end workflow is considered validated when:

- The media file triggers the expected Zap execution.
- Transcript extraction returns usable content.
- Both blog posts and all four social posts are generated.
- Formatter outputs contain the expected title and body fields.
- The configured path conditions select the intended branch.
- Google Sheets receives the expected output values.
- No unresolved critical failures remain in the tested workflow.

## Test Evidence

Supporting evidence should be stored in the `screenshots/` directory, with private data removed.

## Notes

Test case statuses represent recorded execution results and should only be changed after verification.

This document covers functional and negative test scenarios for the AI-powered content repurposing workflow.
