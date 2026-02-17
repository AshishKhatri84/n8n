# 🚀 n8n Automation Workflows

This repository contains multiple production-ready automation workflows
built using **n8n**.

These workflows demonstrate:

-   📧 Email automation
-   📋 Form-based event management
-   🧠 AI-powered news summarization
-   📄 Resume-to-job skill matching
-   🔗 Webhook-based automation APIs
-   📊 Google Sheets integration
-   🤖 OpenAI + AI Agent workflows
------------------------------------------------------------------------

# 📌 Workflows Included

## 🎟 1️⃣ Invitations Workflow

### 🔹 Overview

This workflow automates guest invitations for a **Get-To-Gather event**.

It:

-   Collects submissions from a form
-   Stores responses in Google Sheets
-   Filters entries by submission date
-   Sends batch-specific invitation emails
-   Sends final confirmation email

### ⚙️ Flow Architecture

Form Submission\
⬇\
Append / Update Google Sheet\
⬇\
Date Filter\
⬇\
Switch (Batch 2020 / 2021 / 2022)\
⬇\
Send Gmail Invitation\
⬇\
Merge\
⬇\
Final Confirmation Email


### 🧩 Features

-   📋 Form Trigger
-   📊 Google Sheets Logging
-   📅 Date-based Filtering
-   🔀 Switch-based Routing
-   📧 Batch-specific Gmail notifications
-   📬 Final confirmation email


### 🎯 Use Case

Automating:

-   College events
-   Alumni gatherings
-   Corporate RSVP tracking
-   Event invitation management

------------------------------------------------------------------------

## 📰 2️⃣ AI News Summary Agent

### 🔹 Overview

This workflow builds an **AI-powered daily news summarizer**.

It fetches:

-   🌍 World news (BBC RSS)
-   💻 Tech news (The Verge RSS)

Then:

-   Uses OpenAI model
-   Summarizes last 24 hours
-   Sends daily email at 7 AM



### ⚙️ Flow Architecture

Schedule Trigger (7 AM) OR Manual Trigger\
⬇\
RSS Feeds (World + Tech)\
⬇\
OpenAI Model\
⬇\
AI Agent Summary\
⬇\
Set Output\
⬇\
Send Gmail Summary



### 🧠 AI Configuration

Model Used:

__gpt-4.1-mini__

Prompt Logic:

-   Summarize last 24 hours
-   Separate sections:
    -   "World News:"
    -   "Tech News:"
-   No extra commentary


### 🎯 Use Case

-   Daily executive briefings
-   Personalized AI digest
-   Automated tech monitoring
-   Content curation

------------------------------------------------------------------------

## 📄 3️⃣ Resume Skill Matcher (Capstone Demo)

### 🔹 Overview

This is a webhook-based AI simulation system that:

-   Accepts resume upload (Base64)
-   Extracts text (PDF / TXT)
-   Matches against 20 simulated job roles
-   Calculates skill match percentage
-   Returns top 4 matches


### ⚙️ Flow Architecture

Webhook (POST /resume-upload)\
⬇\
Convert Base64 → Binary\
⬇\
If PDF → Extract PDF\
Else → Extract Text\
⬇\
Merge\
⬇\
Set Resume Text\
⬇\
Generate 20 Job Profiles\
⬇\
Simulated AI Match\
⬇\
Collect Top 4\
⬇\
Return JSON Response



### 📊 Output Example

``` json
{
  "total_jobs_analyzed": 20,
  "top_matches": [
    {
      "job_title": "Machine Learning Engineer",
      "match_percentage": 78,
      "required_skills_present": ["python","modeling"],
      "skill_gaps": ["tensorflow"],
      "overall_assessment": "Strong candidate - recommend interview"
    }
  ]
}
```


### 🧠 Matching Logic

-   Extract keywords from job description
-   Remove stop words
-   Compare against resume text
-   Compute match %

Generate assessment:

-   ≥ 75% → Strong Candidate
-   50-74% → Potential Fit
-   \< 50% → Skill Improvement Recommended


### 🎯 Use Case

-   Resume screening automation
-   HR skill gap analysis
-   AI-based job matching demo
-   Career advisory systems

------------------------------------------------------------------------

# 🛠 Tech Stack

-   n8n
-   Gmail Node
-   Google Sheets Node
-   Webhook Node
-   RSS Feed Reader
-   OpenAI (LangChain Node)
-   JavaScript Code Nodes
-   AI Agent Node

------------------------------------------------------------------------

# 🚀 How to Use

## 1️⃣ Install n8n

``` bash
npm install n8n -g
```

OR use Docker:

``` bash
docker run -it --rm -p 5678:5678 n8nio/n8n
```

------------------------------------------------------------------------

## 2️⃣ Import Workflow

-   Open n8n
-   Click **Import**
-   Upload JSON file
-   Configure credentials:
    -   Gmail OAuth
    -   Google Sheets OAuth
    -   OpenAI API

------------------------------------------------------------------------

# 🔐 Required Credentials

-   Gmail OAuth2
-   Google Sheets OAuth2
-   OpenAI API Key

------------------------------------------------------------------------

# 📈 Skills Demonstrated

-   Automation architecture design
-   Event-driven workflows
-   AI integration in no-code tools
-   Resume parsing logic
-   Dynamic routing
-   Data transformation
-   Workflow orchestration
-   API design via webhooks
