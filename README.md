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

### Key components & data flows

#### Main Components

- **Apify Actor** → Scrapes LinkedIn job listings
- **Google Docs** → Stores and updates tailored resumes
- **Google Sheets** → Logs matched jobs

#### Step-by-step workflow

- **Trigger the workflow on a daily schedule**
- **Fetch base configuration from Google Docs**
- **Initialize global variables and user-defined settings**
- **Generate a structured job search input array**
- **Execute Apify LinkedIn Jobs Scraper for each search input**
- **Poll scraper execution until completion**
- **Retrieve dataset items and remove duplicate job postings**
- **Persist cleaned job data into Google Sheets**
- **Send job alert notifications via Gmail**

---

## 🛠 Tech Stack

- **n8n** – Workflow orchestration
- **Rapid Linkedin Jobs Scraper (Apify Actor)** – Job data collection
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

---

## 👤 Author

**Phan Quoc Anh**  
Automation / Data / AI Engineer  
