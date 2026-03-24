
# AI-Powered Job Email Intelligence System

## Overview

This project is an intelligent email processing system designed to help candidates automatically track and manage their job application pipeline. It reads emails across multiple folders, understands intent using AI and rule-based logic, and categorizes them into meaningful job-related states.

The system evolves over time through a self-learning mechanism, improving classification accuracy without manual retraining.

---

## Key Features

### 1. Multi-Folder Email Processing

* Reads emails from:

  * Inbox
  * Sent Mail
  * Drafts
  * Important
  * Starred

### 2. Intelligent Classification

Emails are categorized into:

* New Opportunity
* Interview
* Offer
* Rejected
* Urgent
* Alerts
* Spam
* Unknown

### 3. Hybrid Intelligence Engine

* LLM-based classification (via Groq API)
* Rule-based keyword scoring
* Self-learning keyword enhancement

### 4. Self-Learning Capability

* Learns new keywords from processed emails
* Stores them in `learned_keywords.json`
* Improves accuracy over time automatically

### 5. Job Pipeline Tracking

* Extracts company and role information
* Tracks latest status per job
* Maintains structured pipeline view

### 6. Data Output

* `email_log.csv` → full email history
* `job_tracker.csv` → latest job status per company-role

---

## System Architecture

Email Ingestion → Classification (LLM + Rules) → Learning Layer → Tracking Engine → CSV Output

---

## Installation

Install dependencies:

```bash
pip install pandas imapclient pyzmail36 nest_asyncio openai
```

---

## Configuration

You will need:

* Gmail account
* Gmail App Password (not your normal password)
* Groq API key

---

## Usage

Run the notebook or script:

```python
tracker_df = run_agent(limit=20)
```

---

## Output Example

| Company  | Role        | Category  | Round           |
| -------- | ----------- | --------- | --------------- |
| ABC Corp | ML Engineer | Interview | Technical Round |

---

## Security Notes

* Never expose API keys in code
* Use environment variables for production
* Revoke keys if accidentally shared

---

## Future Enhancements

* Gmail API integration for auto-labeling
* Streamlit dashboard for visualization
* Auto-reply generation for recruiters
* Interview reminder system
* Multi-agent orchestration

---

## Positioning

This project represents a real-world implementation of:

AI-driven automation + decision intelligence + adaptive learning

---

## License

For educational and personal use.

---

# Standard Operating Procedure (SOP)

AI Job Email Intelligence System

---

## 1. Objective

To ensure consistent, accurate, and automated tracking of job-related emails, enabling candidates to efficiently manage their application pipeline without manual effort.

---

## 2. Scope

This SOP applies to:

* Email ingestion
* Classification
* Data tracking
* Learning mechanism
* Output generation

---

## 3. Pre-Requisites

### Required Setup

* Gmail account with IMAP enabled
* App Password generated via Google Account
* Groq API key
* Python environment with required libraries

---

## 4. System Workflow

### Step 1: Authentication

* User enters:

  * Email ID
  * App Password
  * API Key

### Step 2: Email Extraction

* System connects to IMAP server
* Fetches emails from configured folders
* Extracts subject and body

### Step 3: Classification

#### Primary Method

* LLM processes email content
* Returns structured classification

#### Fallback Method

* Rule-based keyword scoring
* Ensures zero-failure execution

---

### Step 4: Self-Learning

* High-confidence classifications trigger learning
* Keywords extracted and stored
* Learning file updated (`learned_keywords.json`)

---

### Step 5: Data Structuring

Each email is transformed into:

* Timestamp
* Company
* Role
* Category
* Round
* Confidence

---

### Step 6: Tracking Logic

* Group by company + role
* Keep latest status
* Maintain pipeline view

---

### Step 7: Output Generation

Files generated:

* `email_log.csv` → complete history
* `job_tracker.csv` → latest job states

---

## 5. Categories Definition

| Category        | Description                       |
| --------------- | --------------------------------- |
| New Opportunity | Job openings, recruiter outreach  |
| Interview       | Any interview or evaluation stage |
| Offer           | Final selection or offer letter   |
| Rejected        | Application declined              |
| Urgent          | Time-sensitive communication      |
| Alerts          | System or account notifications   |
| Spam            | Promotions or irrelevant emails   |
| Unknown         | No clear classification           |

---

## 6. Error Handling

* IMAP failures → skip folder
* LLM failure → fallback rules
* Parsing errors → default classification
* Empty emails → marked as Unknown

---

## 7. Best Practices

* Use limited email fetch size during testing
* Regularly review generated CSV files
* Monitor learned keywords for noise
* Avoid exposing credentials in notebooks

---

## 8. Maintenance

### Weekly

* Review classification accuracy
* Clean learned keywords if needed

### Monthly

* Update keyword base
* Optimize classification rules

---

## 9. Risk Management

| Risk                 | Mitigation                |
| -------------------- | ------------------------- |
| API key exposure     | Use environment variables |
| Misclassification    | Hybrid model + learning   |
| Data overload        | Limit fetch size          |
| Email parsing issues | Fallback handling         |

---

## 10. Future Scalability

* Integration with Gmail API
* UI dashboard implementation
* Multi-agent orchestration
* Enterprise workflow automation

---

## 11. Conclusion

This system transforms raw email data into structured job intelligence, enabling smarter decision-making and ensuring no opportunity is missed.

---
