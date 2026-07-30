# Architecture

## Overview

RapidResponse is a lightweight snippet management platform built on Google Apps Script and Google Sheets.

Each user receives their own private snippet repository, eliminating the need for a centralized database while keeping setup simple.

## High-Level Architecture

```text
User
 │
 ▼
RapidResponse
 │
 ├── Smart Search
 ├── Slash Commands
 ├── Snippet Management
 ├── Clipboard Workflow
 │
 ▼
Google Apps Script
 │
 ▼
Google Drive
 │
 ▼
RP Spreadsheet
```

## Storage Model

Each user owns a spreadsheet named:

```text
RP
```

The spreadsheet contains:

```text
Canned Responses
```

with:

| Column | Description |
|----------|----------|
| Code | Slash command |
| Name | Friendly name |
| Text | Response content |

## User Flow

```text
Create Snippet
        ↓
Save to RP Spreadsheet
        ↓
Search with /
        ↓
Select Suggestion
        ↓
Insert Response
        ↓
Press Enter
        ↓
Copy to Clipboard
        ↓
Paste Anywhere
```
