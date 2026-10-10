# AI-Powered Business Development Automation

## Project Overview

An AI-powered, multi-agent sales automation workflow designed to streamline prospect discovery, CRM data entry, and outbound email preparation for a fictional accounting software company, AccountAI.

The system uses a central AI agent to coordinate specialized subagents and connects business data sources and productivity tools through n8n.

**Project status:** In progress — partial testing  
**Automation platform:** n8n  
**AI integration:** OpenAI  
**Business domain:** Sales development and revenue operations

## Business Problem

Sales development involves several repetitive tasks:

- Finding potential customers that match an ideal customer profile (ICP).
- Collecting and structuring prospect information.
- Recording organizations, contacts, and leads in a CRM.
- Preparing personalized outbound sales emails.
- Notifying the user about workflow outcomes.

Performing these tasks manually can consume time and lead to inconsistent records. This project explores how AI agents and workflow automation can coordinate these activities.

## Proposed Solution

A central Business Development Manager agent receives an ICP document and coordinates specialized agents to support the sales process.

### System Architecture

1. **Document ingestion:** A Google Drive trigger detects a newly created file. The workflow downloads the file and extracts text from the PDF.
2. **Sales manager agent:** An AI agent interprets the ICP and coordinates the downstream tasks.
3. **Prospecting subagent:** Uses MCP-connected tools to search for potential prospects and gather relevant company and contact information.
4. **RevOps subagent:** Structures prospect information and prepares organization, person, and lead records in Pipedrive.
5. **SDR subagent:** Retrieves contact records and creates outbound email drafts in Gmail.
6. **Notifications:** Pushbullet sends notifications based on the workflow's conditional routing.

The architecture above describes the intended process. End-to-end execution and the correct transfer of data between stages still need verification.

## Technology Stack

- **n8n:** Workflow orchestration and agent coordination
- **OpenAI:** Language-model reasoning and structured information generation
- **MCP tools:** External search and website research capabilities
- **Google Drive:** ICP document intake
- **Pipedrive:** CRM record management
- **Gmail:** Email draft creation
- **Pushbullet:** Workflow notifications

## Current Implementation

The main workflow and specialized subagents have been created in n8n. A successful execution and working Pushbullet notifications have been observed.

However, the full sequence—from document ingestion through prospect discovery, CRM record creation, and email drafting—has not yet been verified end to end.

## Testing and Validation

The next validation steps are to establish that:

- The ICP document is downloaded and parsed correctly.
- The prospecting agent returns relevant, structured prospect information.
- The RevOps agent creates the intended CRM records without unintended duplicates.
- The SDR agent generates appropriate Gmail drafts for the intended contacts.
- The workflow reports failures and outcomes accurately.

Testing should use appropriate test data and avoid sending unsolicited emails. Credentials and private contact data must not be included in public project materials.

## Limitations and Future Improvements

- Validate prospect information and the provenance of contact details.
- Improve CRM duplicate detection and organization-person associations.
- Ensure email drafts are created only for contacts identified in the current workflow run.
- Add robust error handling and clear per-stage execution reporting.
- Evaluate output quality, reliability, and processing time with controlled test cases.

## Evidence

Screenshots, representative outputs, and validation results will be added after the relevant stages have been verified. Sensitive information and credentials will be excluded.

## Skills Demonstrated

- Multi-agent workflow design
- AI-assisted information extraction
- Structured output handling
- API-connected business process automation
- CRM and email workflow integration
- Workflow testing and reliability analysis
