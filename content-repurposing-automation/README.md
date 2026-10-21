# AI-Powered Content Repurposing Automation

### End-to-End Workflow Automation Using Zapier, Google Gemini & Google Workspace

An AI-powered workflow designed to transform audio and video content into multiple reusable content formats through automated transcription, content generation, data transformation, conditional routing, and structured logging.

## Project Overview

This project demonstrates a 20-step Zapier workflow integrating AI services and Google Workspace applications to automate content repurposing.

**Input:** One audio or video file

**Generated Outputs:**
- 2 blog posts with different content angles
- 2 Instagram captions
- 2 LinkedIn posts
- Structured content records in Google Sheets

## Problem Statement

Manually repurposing audio and video content into blog articles and social media posts requires repetitive transcription, writing, formatting, and data entry.

This project aims to reduce repetitive tasks by building an event-driven automation workflow.

## Solution Architecture

The automation follows five main phases:

### Phase 1: File Detection and Transcription
1. Google Drive monitors a designated folder for new media files.
2. AI by Zapier extracts the transcript from the uploaded media.

### Phase 2: AI Blog Generation
3. Google Gemini generates Blog Post 1 using a primary content angle.
4. Zapier Formatter extracts the blog title.
5. Zapier Formatter extracts the blog body.
6. Google Gemini generates Blog Post 2 using an alternative angle.
7. Zapier Formatter extracts the second blog title.
8. Zapier Formatter extracts the second blog body.

### Phase 3: Social Media Content Generation
9. Google Gemini generates Instagram Caption 1.
10. Google Gemini generates LinkedIn Post 1.
11. Google Gemini generates Instagram Caption 2.
12. Google Gemini generates LinkedIn Post 2.

### Phase 4: Validation and Conditional Routing
13. Zapier Filter validates content based on configured criteria.
14. Zapier Paths evaluates conditional routing rules.

The workflow includes:
- Path A: Faith-Based Content
- Path B: General Content

### Phase 5: Structured Data Logging
15. Google Sheets records faith-based content.
16. Additional Formatter steps process general content fields.
17. Google Sheets records general content.

## Technology Stack

| Technology | Purpose |
|---|---|
| Zapier | Workflow orchestration |
| Google Drive | File monitoring and triggering |
| AI by Zapier | Transcript extraction |
| Google Gemini | AI-powered content generation |
| Zapier Formatter | Data parsing and transformation |
| Zapier Filter | Conditional validation |
| Zapier Paths | Workflow branching |
| Google Sheets | Content logging |

## Key Features

- Event-driven automation
- AI-assisted transcript extraction
- Multi-format content generation
- Automated title and body parsing
- Conditional content routing
- Structured data logging
- Integration across multiple applications

## Workflow Screenshot

![Zapier Workflow](screenshots/full-workflow.png)

## Testing Approach

The workflow is designed to be validated through:

- Google Drive trigger testing
- Transcript extraction verification
- AI-generated content inspection
- Formatter output validation
- Filter and path condition testing
- Google Sheets field mapping verification
- End-to-end execution testing

## QA Test Execution Summary

| Metric | Result |
|---|---|
| Total Test Cases | 16 |
| Functional Test Cases | 12 |
| Functional Tests Passed | 12 |
| Negative Test Cases | 4 |
| Negative Tests Executed | 0 |
| Functional Pass Rate | 100% |
| Overall Testing Status | Partial — Negative Testing Pending |

### Testing Limitations

All 12 functional test cases passed during workflow execution, based on recorded testing results.

Negative test scenarios were not executed because Zapier subscription/trial access expired.

The workflow demonstrated successful functional execution, but error handling and failure recovery require additional validation.

For detailed test scenarios and execution results, see [TEST_CASES.md](TEST_CASES.md).

## Project Status

**Implemented — Functional Testing Passed; Negative Testing Pending.**

## Business Value

This automation demonstrates how AI and no-code integrations can reduce repetitive content production activities, improve content organization, and support scalable workflow design.

## Future Improvements

- Automated error notifications
- Duplicate file detection
- Human approval workflow
- Content quality validation
- Automated social media publishing
- Processing time and performance monitoring

## Project Information

**Category:** AI Workflow Automation

**Tools:** Zapier, Google Gemini, Google Drive, Google Sheets

**Implementation:** 20-step workflow with conditional paths

**Author:** Janessa Balontong

---

*Portfolio project demonstrating workflow automation, AI integration, conditional logic, data transformation, and quality assurance practices.*
