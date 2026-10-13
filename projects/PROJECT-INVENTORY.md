# Project Inventory

This document tracks the implementation status, verification status, and portfolio readiness of my AI automation projects.

Projects are marked as portfolio-ready only after their core functionality has been reviewed, tested, and supported with appropriate documentation or evidence.

## Project Status

| Project | Implementation Status | Portfolio Status |
|---|---|---|
| [Lead Qualification & CRM Automation](ai-lead-qualification-crm-automation) | Verified - core workflow tested | Portfolio Ready |
| [AI Customer Support Triage & Response Assistant](ai-customer-support-triage-response-assistant) | Verified - core workflow tested | Portfolio Ready |
| [AI Document Processing & Data Extraction](ai-document-processing-data-extraction) | Verified - core workflow tested | Portfolio Ready |
| First AI Agent | To be verified | Under review |
| Equity Portfolio Rebuilder | To be verified | Under review |
| Funny Stock Lookup | To be verified | Under review |
| Business Development Manager | To be verified | Under review |
| RevOps Sub-Agent | To be verified | Under review |
| SDR Sub-Agent | To be verified | Under review |
| Prospecting Sub-Agent | To be verified | Under review |
| Prospecting MCP | To be verified | Under review |

# Verified Portfolio Projects

## 1. Lead Qualification & CRM Automation

**Status:** Portfolio Ready

An end-to-end lead intake and qualification automation built with **n8n, Google Sheets, JavaScript, and Gmail**.

The workflow receives leads through a webhook, validates and normalizes incoming data, checks for duplicate records, calculates a deterministic lead score, classifies leads as **Hot, Warm, or Cold**, stores qualified lead data in Google Sheets, and automatically sends a Gmail notification when a Hot lead is detected.

### Verified Functionality

- Webhook-based lead intake
- Required-field validation
- Lead data normalization
- Duplicate lead detection
- Deterministic lead scoring
- Hot / Warm / Cold lead qualification
- Google Sheets CRM-style storage
- Conditional routing based on qualification
- Automated Gmail notification for Hot leads
- Testing with multiple lead profiles

### Verification Evidence

- Successful end-to-end workflow execution
- Hot lead qualification tested successfully
- Warm lead qualification tested successfully
- Cold lead qualification tested successfully
- Invalid/missing required-field routing tested
- Google Sheets records verified
- Gmail Hot Lead Alert verified
- Workflow overview screenshot captured
- Qualification results screenshot captured
- Hot Lead Alert screenshot captured
- n8n workflow exported as JSON
- Project README documentation completed

### Portfolio Materials

The project repository contains:

- Detailed project README
- Workflow architecture screenshot
- Google Sheets results screenshot
- Hot Lead Alert screenshot
- Exported n8n workflow JSON

**Tools:** n8n · JavaScript · Google Sheets · Gmail · Webhooks

[View project documentation →](ai-lead-qualification-crm-automation)

---

## 2. AI Customer Support Triage & Response Assistant

**Status:** Portfolio Ready

An AI-powered customer support automation built with **n8n, OpenAI, Google Sheets, JavaScript, and Gmail**.

The workflow receives support tickets through a webhook, validates and normalizes the incoming data, uses an OpenAI model to analyze and classify each ticket, stores structured results in a support queue, and automatically alerts the support team when a ticket is classified as **High** or **Urgent** priority.

The system uses a human-in-the-loop design so AI-generated analysis and draft responses can be reviewed before customer-facing action is taken.

### Verified Functionality

- Webhook-based support ticket intake
- Required-field validation
- Ticket data normalization
- OpenAI-powered ticket analysis
- Structured AI output parsing
- Ticket category classification
- Low / Medium / High / Urgent priority classification
- Customer sentiment classification
- AI-generated ticket summaries
- AI-generated recommended actions
- AI-generated draft responses for human review
- Google Sheets support queue storage
- Conditional routing based on priority
- Automated Gmail alerts for High and Urgent tickets
- Human-review safeguards
- Invalid-input rejection

### Verification Evidence

The workflow was tested with multiple scenarios:

- Billing ticket classified as High priority
- Account Access ticket classified as High priority
- Product Question classified as Low priority
- Account Access ticket classified as Urgent priority
- Low-priority ticket correctly routed without an alert
- High-priority ticket correctly triggered an email alert
- Urgent ticket correctly triggered an email alert
- Missing required email correctly failed validation
- Google Sheets support queue verified
- Formatted Gmail priority notification verified
- Structured OpenAI output verified
- Successful end-to-end workflow execution
- n8n workflow exported and sanitized for public use
- Project README documentation completed

### Portfolio Materials

The project repository contains:

- Detailed project README
- Complete workflow architecture screenshot
- Google Sheets support queue results screenshot
- Sanitized priority ticket alert screenshot
- Sanitized n8n workflow JSON

### Human-in-the-Loop Design

The AI assists with ticket analysis and response preparation but does not autonomously perform customer account or financial actions.

The workflow includes prompt safeguards designed to prevent the AI from claiming that refunds, cancellations, credits, account changes, or similar business actions have already been completed.

AI-generated responses are treated as drafts for human review.

**Tools:** n8n · OpenAI · JavaScript · Google Sheets · Gmail · Webhooks · Structured Output

[View project documentation →](ai-customer-support-triage-response-assistant)

---

## 3. AI Document Processing & Data Extraction

**Status:** Portfolio Ready

An AI-assisted document processing workflow built with **n8n, OpenAI, JavaScript, Google Sheets, and Gmail**.

The workflow accepts an invoice PDF through an n8n form, extracts the document text, uses an OpenAI model to convert the unstructured invoice content into structured data, validates the extracted financial information using deterministic JavaScript logic, and routes the invoice according to the validation result.

Valid invoices are stored in a dedicated Google Sheets record. Invoices that fail validation are routed to a separate human-review queue and trigger an internal Gmail alert containing the invoice details and detected validation error.

### Workflow Architecture

The workflow follows this processing sequence:

1. PDF invoice submission through an n8n form
2. Text extraction from the uploaded PDF
3. AI-assisted structured invoice data extraction
4. Deterministic invoice validation
5. Conditional valid/invalid routing
6. Google Sheets storage for valid invoices
7. Human-review queue storage for invalid invoices
8. Gmail notification when human review is required

### Extracted Invoice Data

The AI extraction step produces structured fields including:

- Invoice number
- Vendor name
- Invoice date
- Due date
- Currency
- Purchase order
- Subtotal
- Tax
- Total
- Line-item descriptions
- Quantities
- Unit prices
- Line-item amounts

### Verified Functionality

- PDF upload through an n8n form
- PDF text extraction
- OpenAI-powered invoice data extraction
- Structured JSON output
- Invoice field extraction
- Line-item extraction
- Deterministic JavaScript validation
- Subtotal and tax validation against invoice total
- Valid / invalid invoice classification
- Conditional routing based on validation result
- Google Sheets storage for valid invoices
- Separate Google Sheets human-review queue
- Validation error recording
- Automated Gmail notification for invoices requiring review
- Human-in-the-loop exception handling

### Verification Evidence

The workflow was tested with both valid and invalid invoice scenarios.

#### Valid Invoice Test

Invoice **INV-2026-1048** was successfully:

- Uploaded as a PDF
- Converted to text
- Processed by the AI extraction step
- Converted into structured invoice data
- Validated successfully
- Classified as **Valid**
- Routed through the valid branch
- Stored in the valid invoice Google Sheet

The verified financial values included:

- Subtotal: 860
- Tax: 86
- Total: 946

The validation correctly confirmed that:

**860 + 86 = 946**

#### Invalid Invoice Test

Invoice **INV-2026-1049** was tested with an inconsistent invoice total.

The workflow identified:

- Subtotal: 860
- Tax: 86
- Invoice Total: 1046

The validation correctly detected that:

**860 + 86 = 946**, which does not match the stated invoice total of **1046**.

The invoice was therefore:

- Classified as **Needs Review**
- Routed through the false/review branch
- Stored in the Human Review Queue
- Recorded with the validation error
- Used to trigger a Gmail human-review notification

The recorded validation error stated that the calculated subtotal plus tax was 946 while the invoice total was 1046.

### Human-in-the-Loop Design

The workflow intentionally separates **AI extraction** from **deterministic validation**.

The AI is responsible for transforming unstructured invoice text into structured data. Financial validation is then performed separately using deterministic JavaScript logic.

Invoices that fail validation are **not automatically approved**.

Instead, they are routed to a human-review queue and an internal notification is generated so that the original document and extracted information can be reviewed before further action is taken.

### Portfolio Materials

The project repository contains:

- Detailed project README
- Complete workflow architecture screenshot
- Valid invoice results screenshot
- Human Review Queue screenshot
- Sanitized Human Review Alert screenshot
- Sanitized n8n workflow JSON

### Public Workflow Safety

The publicly shared workflow JSON is sanitized for portfolio use.

Sensitive or environment-specific information such as credentials and private account configuration should not be included in the public workflow export. Anyone importing the workflow must configure their own credentials and integrations.

### Limitations

This project is a portfolio demonstration of an AI-assisted document processing architecture rather than a production accounting or payment system.

The workflow:

- Does not autonomously approve payments
- Does not execute payments
- Does not modify accounting records outside the configured demonstration sheets
- Requires human review when validation fails
- Depends on the quality and readability of the uploaded PDF
- Uses AI for extraction, so extracted information should be verified before consequential business action

**Tools:** n8n · OpenAI · JavaScript · Google Sheets · Gmail · PDF Processing · Structured Output

[View project documentation →](ai-document-processing-data-extraction)

---

# Projects Under Review

The following projects exist in my automation workspace but are not yet presented as completed portfolio projects.

They will be reviewed individually before their implementation status or capabilities are publicly claimed as verified.

- First AI Agent
- Equity Portfolio Rebuilder
- Funny Stock Lookup
- Business Development Manager
- RevOps Sub-Agent
- SDR Sub-Agent
- Prospecting Sub-Agent
- Prospecting MCP

---

# Verification Checklist

Before a project is marked as portfolio-ready, I review:

- [ ] Intended problem and expected outcome
- [ ] Actual workflow implementation
- [ ] Required credentials and integrations
- [ ] Successful test execution
- [ ] Output quality and error handling
- [ ] Conditional routing behavior
- [ ] Screenshots or other demonstration evidence
- [ ] Sensitive information removed from public materials
- [ ] Clear explanation of limitations
- [ ] Exported workflow or reproducible implementation where appropriate
- [ ] Project documentation completed

---

# Publication Rule

A project is presented as **Portfolio Ready** only after its core functionality has been tested successfully and the available evidence supports the claims made in its documentation.

Projects that have not yet been fully reviewed remain marked as **Under review** or **To be verified** rather than being presented as completed implementations.
