# 🔍 LinkedIn Job Search Automation with n8n

An end-to-end **LinkedIn job search automation workflow** built with **n8n**, designed to automatically collect, clean, deduplicate, filter, and deliver job postings based on dynamic search configurations.

This project focuses on **workflow architecture, data quality, and cost-aware automation**, not just simple scraping.

---

## 🚀 Key Features

- ⏰ **Scheduled automation** using n8n Schedule Trigger
- 📄 **Dynamic configuration** via Google Docs (no hard-coded inputs)
- 🔁 **Loop-based batch processing** for multiple job queries
- 🧹 **Deduplication logic** to remove repeated job postings
- 🎯 **Business-rule filtering** to keep only relevant jobs
- 📊 **Structured storage** in Google Sheets
- 📧 **Automated email notifications** via Gmail

---

## 🧠 Workflow Overview

![n8n workflow](n8n-automation.png)

### High-level Architecture

1. **Schedule Trigger**  
   Automatically triggers the workflow on a defined schedule.

2. **Get Configuration (Google Docs)**  
   Loads job search parameters such as keywords, locations, and filters.

3. **Set Global Variables**  
   Initializes shared variables for use across the workflow.

4. **Prepare Job Input Array**  
   Transforms raw configuration data into a structured array of job search inputs.

5. **Loop Over Jobs**  
   Iterates through each job query independently.

6. **Format Input**  
   Normalizes job search parameters for the scraper.

7. **Run LinkedIn Jobs Scraper**  
   Executes the scraping task for each job query.

8. **Remove Duplicate Jobs**  
   Eliminates duplicated job postings across multiple searches.

9. **Set Job Details**  
   Cleans and standardizes job fields (title, company, location, URL, etc.).

10. **Filter Relevant Jobs**  
    Applies business rules to keep only matching job postings.

11. **Store Results (Google Sheets)**  
    Appends or updates structured job data in Google Sheets.

12. **Send Notifications (Gmail)**  
    Sends summarized job alerts via email.

---

## 🛠 Tech Stack

- **n8n** – Workflow orchestration
- **LinkedIn Jobs Scraper (Apify Actor)** – Job data collection
- **Google Docs API** – Dynamic configuration input
- **Google Sheets API** – Data storage
- **Gmail API** – Email notifications

---

## ⚙️ Design Highlights

- **Config-driven workflow design** (Google Docs as input source)
- **Separation of concerns** between configuration, processing, and output
- **Loop & batch processing** for scalability
- **Deduplication and normalization** to ensure data quality
- **Cost-aware automation** to minimize unnecessary API calls

---

## 📊 Output Data Structure

Each job record includes:

- Job title  
- Company name  
- Location  
- Job URL  
- Search keyword  
- Timestamp  

---

## 📌 Use Cases

- Daily LinkedIn job alert automation
- Job market monitoring
- Automated job tracking for candidates
- Data collection for job trend analysis

---

## 🔐 Notes

- API keys and credentials are **not included** in this repository.
- Workflow screenshots are provided for architectural reference.
- The `workflow.json` file should be imported into n8n and configured with your own credentials.

---

## 📄 License

MIT License

---

## 👤 Author

**Phan Quoc Anh**  
Automation / Data / AI Engineer  
