# 📄 Resume Analyzer Automation (n8n)

This workflow automates **resume screening**: it extracts candidate details from resumes sent via Gmail, analyzes them using AI, and saves the results into Google Sheets

---

## 🚀 Workflow Overview

1. **Gmail Trigger** – Watches for new emails with resumes (PDF) attached.
2. **Upload & Download File** – Stores the resume in Google Drive, then downloads it.
3. **Extract from File** – Extracts text content from the PDF.
4. **Information Extractor** – Pulls out candidate details (name, email, phone number).
5. **AI Agent (OpenAI)** –

   * Summarizes CV (education, job history, skills).
   * Evaluates fit for a given job.
   * Assigns a **Relevance Score (1–10)** with a justification.
6. **Edit & Format** – Structures all data into clean JSON.
7. **Append to Google Sheets** – Saves candidate details + score into a central spreadsheet.

---

## ⚙️ Setup Instructions

1. Import the file `Resume Analyzer.json` into your n8n instance.
2. Configure the following credentials in n8n:

   * **Gmail API** (to receive resumes)
   * **Google Drive API** (to store and fetch resumes)
   * **Google Sheets API** (to save results)
   * **OpenAI API** (for AI-based evaluation)
3. Update the Google Sheets ID inside the workflow (currently points to *List of candidates*).
4. Activate the workflow.

---

## 📂 Files in This Repo

* `Resume Analyzer.json` → Workflow definition.
* `Resume Analyzer 1.jpg` → Visual diagram of the workflow.

---

## 🔑 Requirements

* n8n (cloud or self-hosted)
* Gmail account
* Google Drive account
* Google Sheets account
* OpenAI API key

---

## 📌 Notes

* The evaluation logic is controlled by the **system prompt** in the AI Agent node. You can edit it to adjust scoring criteria.
* Works best with **PDF resumes**. Other formats may need additional nodes for parsing.

---

Do you also want me to add a **badges section** (like `Built with n8n`, `Uses OpenAI`, `Google APIs`) at the top of both READMEs to make them look more professional?
