# AI Automation Portfolio

I build and explore AI-powered automation solutions that connect workflow orchestration, APIs, AI tools, and business systems to solve practical problems.

My work focuses on designing automated workflows, integrating external services, implementing business logic, building AI-assisted systems, and improving workflow reliability through structured testing and debugging.

## Core Areas

- **Workflow Automation:** Designing and orchestrating multi-step automated workflows using n8n.
- **AI-Powered Automation:** Integrating language models into workflows for classification, analysis, structured data extraction, and response generation.
- **AI & Agent Workflows:** Exploring AI-assisted and agent-based automation systems.
- **Document Processing:** Extracting structured business data from documents and routing results through validation workflows.
- **API & Service Integration:** Connecting external services, webhooks, and structured data.
- **Workflow Logic:** Implementing validation, conditional routing, data transformation, scoring, and business rules.
- **Testing & Reliability:** Testing workflow paths, validating outputs, debugging failures, and documenting verified behavior.

## Selected Projects

### [Lead Qualification & CRM Automation](projects/ai-lead-qualification-crm-automation)

An end-to-end lead intake and qualification automation built with **n8n, Google Sheets, JavaScript, and Gmail**.

The workflow receives leads through a webhook, validates and normalizes incoming data, checks for duplicate records, calculates a deterministic lead score, classifies leads as **Hot, Warm, or Cold**, stores qualified lead data in Google Sheets, and automatically sends an email notification when a Hot lead is detected.

**Key features:**

- Webhook-based lead intake
- Required-field validation
- Data normalization
- Duplicate lead detection
- Deterministic lead scoring
- Hot / Warm / Cold qualification
- Qualification reason generation
- Google Sheets CRM-style storage
- Conditional Gmail alerts for Hot leads
- Multiple test scenarios covering different lead profiles

**Tools:** n8n · JavaScript · Google Sheets · Gmail · Webhooks

[View project documentation →](projects/ai-lead-qualification-crm-automation)

---

### [AI Customer Support Triage & Response Assistant](projects/ai-customer-support-triage-response-assistant)

An AI-powered customer support automation built with **n8n, OpenAI, Google Sheets, JavaScript, and Gmail**.

The workflow receives support tickets through a webhook, validates and normalizes incoming data, uses an OpenAI model to classify and analyze each ticket, converts the AI response into structured data, stores the result in a support queue, and automatically alerts the support team when a ticket is classified as **High** or **Urgent** priority.

The system follows a **human-in-the-loop design**, where AI-generated analysis and draft responses are reviewed before customer-facing action is taken.

**Key features:**

- Webhook-based support ticket intake
- Required-field validation
- Ticket data normalization
- OpenAI-powered ticket analysis
- Structured AI output parsing
- Category classification
- Low / Medium / High / Urgent priority classification
- Sentiment classification
- AI-generated summaries
- Recommended-action generation
- Draft response generation for human review
- Google Sheets support queue
- Conditional High / Urgent priority routing
- Automated Gmail priority alerts
- Human-review and authorization safeguards
- Multiple ticket scenarios and invalid-input testing

**Tools:** n8n · OpenAI · JavaScript · Google Sheets · Gmail · Webhooks · Structured Output

[View project documentation →](projects/ai-customer-support-triage-response-assistant)

---

### [AI Document Processing & Data Extraction](projects/ai-document-processing-data-extraction)

An AI-assisted invoice processing automation built with **n8n, OpenAI, JavaScript, Google Sheets, Gmail, and PDF processing**.

The workflow accepts an invoice PDF through an n8n form, extracts its text, uses an OpenAI model to convert unstructured invoice content into structured data, validates the extracted financial information using deterministic JavaScript logic, and routes the invoice according to the validation result.

Valid invoices are stored in Google Sheets. Invoices that fail validation are routed to a separate **Human Review Queue** and trigger an internal Gmail alert containing the invoice details and validation error.

**Key features:**

- PDF invoice upload through an n8n form
- Automated PDF text extraction
- AI-powered structured invoice data extraction
- JSON Schema structured output
- Invoice and line-item extraction
- Deterministic JavaScript validation
- Subtotal + tax vs. invoice total verification
- Valid / Needs Review classification
- Conditional workflow routing
- Google Sheets storage for valid invoices
- Separate Human Review Queue for failed validation
- Validation error recording
- Automated Gmail human-review alerts
- Human-in-the-loop exception handling
- Valid and invalid invoice test scenarios

The architecture intentionally separates **AI extraction from deterministic validation**. AI converts the document into structured data, while JavaScript independently applies the financial validation rules. Invoices that fail validation are not automatically approved.

**Tools:** n8n · OpenAI · JavaScript · Google Sheets · Gmail · PDF Processing · Structured Output

[View project documentation →](projects/ai-document-processing-data-extraction)

---

### Business Development Automation

Multi-workflow business development automation exploring prospecting, sales development, RevOps, workflow orchestration, and CRM-related processes.

**Status:** In review — documentation will be expanded as individual workflow behavior is verified.

---

### Revenue Operations & Prospecting Workflows

A collection of n8n workflows exploring prospect research, lead processing, RevOps operations, and sales automation.

**Status:** In review — projects will be documented individually as their implementations and test results are verified.

## Technical Toolkit

- **Workflow Orchestration:** n8n
- **AI Integration:** OpenAI chat models, prompt design, structured AI output, classification, summarization, data extraction, and response drafting
- **Document Processing:** PDF text extraction, structured invoice extraction, and document-to-structured-data workflows
- **Automation Logic:** JavaScript, conditional routing, validation, scoring, and data transformation
- **Integrations:** Webhooks, APIs, Google Sheets, Gmail, and external services
- **AI & Agent Systems:** AI-assisted workflows and agent-based automation experiments
- **Data Handling:** JSON, JSON Schema, structured workflow data, and structured LLM output
- **Human-in-the-Loop Design:** AI-assisted processing with human review before sensitive, financial, or customer-facing actions
- **Development Practices:** Testing, debugging, documentation, workflow validation, sanitization of public artifacts, and version control
- **Version Control:** GitHub

## Portfolio Approach

Projects in this repository are documented based on implemented and verified functionality.

Where a workflow is still experimental, partially tested, or under development, its status is stated rather than presenting unfinished functionality as complete.

Each completed case study aims to document:

- The business problem
- Workflow architecture
- Implementation approach
- Tools and integrations
- Business logic
- AI integration where applicable
- Testing evidence
- Human-review considerations where applicable
- Limitations
- Potential improvements
- Reproducible workflow artifacts where appropriate

## Professional Development

I am continuing to expand my practical skills in AI automation, AI application development, agentic systems, API integration, software engineering, document processing, and production-oriented workflow design.

This portfolio will grow as additional projects are implemented, tested, and documented.

## Contact

Professional contact information will be added here.
