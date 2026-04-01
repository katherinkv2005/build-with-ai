# Shadow AI Governance Tool

## Problem Statement
Employees are pasting sensitive company data — source code, legal documents, customer records, financial spreadsheets — into free third-party AI tools and LLMs without IT's knowledge. Standard DLP (Data Loss Prevention) tools were not built to intercept browser-based AI interactions, leaving enterprises with an invisible, unaudited data leakage channel they cannot see or control.

## Project Description
Shadow AI Governance Tool is a browser extension (Manifest V3) that sits between the employee and any third-party AI platform. Before any data leaves the local environment, the extension intercepts it, classifies it for sensitivity using an on-device NLP model, and automatically replaces PII and confidential identifiers with anonymous tokens.
For example, if an employee pastes a customer spreadsheet into an LLM chat window, the extension silently replaces real names, account numbers, and emails with tokens like [CUSTOMER_001] and [ACCOUNT_4829] — the AI still processes a coherent input, but no real data ever leaves the device. IT admins get a full audit log of every interaction.
What makes it useful:

Zero latency impact — classification runs locally in WebAssembly
Employees face no friction; redaction is invisible and automatic
Fully configurable policy engine lets IT define rules by data type, department, or destination platform
Audit logs are SIEM-ready (Splunk, Datadog, Google Chronicle)

---

## Google AI Usage
### Tools / Models Used
-Gemini Nano (on-device) — Local PII classification and sensitive data detection
Google Chrome Extensions API (Manifest V3) — Browser-level content interception
Google Chronicle / Security Operations API — Audit log ingestion and SIEM integration
Gemini API — Policy recommendation engine for IT admins based on detected data patterns 

### How Google AI Was Used
Explain clearly how AI is integrated into your project.
Gemini Nano runs entirely on-device inside the browser extension's service worker, classifying clipboard and form content against 12 PII categories (names, emails, financials, health data, etc.) without sending any data to an external server. This is critical — a governance tool that sends data to the cloud to check if data is sensitive would be self-defeating. When the IT admin dashboard is open, the Gemini API analyzes aggregated (anonymized) usage patterns across the organization and recommends policy updates — for instance, flagging that 80% of redactions are happening on a specific AI platform and suggesting it be blocked entirely. Audit events stream to Google Chronicle for enterprise-grade retention and alerting.
---

## Proof of Google AI Usage
Attach screenshots in a `/proof` folder:

![AI Proof](./proof/screenshot1.png)

---

## Screenshots 
Add project screenshots:


screenshot1.png
---

## Demo Video
Upload your demo video to Google Drive and paste the shareable link here(max 3 minutes).
[Watch Demo](#)

---

## Installation Steps

```bash
# Clone the repository
git clone <your-repo-link>

# Go to project folder
cd project-name

# Install dependencies
npm install

# Run the project
npm start
