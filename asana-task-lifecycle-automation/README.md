# Asana Task Lifecycle & Client Communication Automation

### Multi-Path Workflow Automation Using Zapier, Asana, Google Drive & Gmail

A status-driven workflow automation project designed to coordinate task management, lead follow-ups, document retrieval, and client communications using Zapier.

## Project Overview

This project demonstrates how an Asana task update can trigger different automated actions based on its current status.

The workflow uses five conditional paths to manage client-related activities, including folder creation, social media task creation, follow-up emails, delayed checks, welcome messages, and service notifications.

**Primary objective:** Reduce repetitive administrative tasks and standardize client communication throughout different stages of a task lifecycle.

## Workflow Architecture

![Asana Task Lifecycle Workflow](screenshots/asana-task-lifecycle-workflow.png)

## Technology Stack

| Technology | Purpose |
|---|---|
| Asana | Task status updates and task creation |
| Zapier | Workflow orchestration |
| Paths by Zapier | Status-based conditional branching |
| Google Drive | Folder creation and PDF retrieval |
| Gmail | Automated client communications |
| Delay by Zapier | Scheduled follow-up intervals |
| Filter by Zapier | Conditional follow-up processing |

## Workflow Process

### Step 1 — Asana Trigger

The workflow begins when a task is updated in Asana.

The task status determines which conditional path will execute.

### Step 2 — Conditional Routing

Paths by Zapier evaluates the task status and routes execution into one of five branches.

## Five Workflow Paths

### Path 1 — Ready to Start

**Trigger condition:** Task status is Ready to Start.

Actions:

1. Create a lead folder in Google Drive.
2. Create a social media content task in Asana.

**Intended outcome:** Prepare the necessary project workspace and initiate content-related activities.

### Path 2 — No Response

**Trigger condition:** Task status is No Response.

Actions:

1. Send an initial follow-up email through Gmail.
2. Wait using Delay by Zapier.
3. Check for a lead response using Gmail.
4. Evaluate the response condition using Filter by Zapier.
5. Send a second follow-up email when the filter condition is satisfied.

**Intended outcome:** Automate repeated follow-up activities while using
