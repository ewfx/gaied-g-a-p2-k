# 🚀 Project Name  
Gen AI Orchestrator for Email and Document Triage/Routing 


## 📌 Table of Contents
- [Introduction](#introduction)
- [Demo](#demo)
- [Inspiration](#inspiration)
- [What It Does](#what-it-does)
- [How We Built It](#how-we-built-it)
- [Challenges We Faced](#challenges-we-faced)
- [How to Run](#how-to-run)
- [Tech Stack](#tech-stack)
- [Team](#team)

---

## 🎯 Introduction
Our Email Classification System is an automated solution that transforms how banks handle customer communications. By leveraging artificial intelligence to analyze incoming emails, the system intelligently categorizes requests, extracts key information, and routes messages to the appropriate teams - all without human intervention. This dramatically reduces manual processing time, ensures consistent handling, and improves response times for customers.
Banks receive hundreds of emails daily across various departments, with requests ranging from loan modifications to transaction inquiries. Traditionally, staff manually sort, categorize, and route these messages, creating bottlenecks and inconsistent customer experiences. Our system eliminates these inefficiencies by automating the entire process from receipt to routing.

## 🎥 Demo

🖼️ Screenshots:

![Screenshot 1]([link-to-image](https://drive.google.com/file/d/1o4bAU1DimRdud9VcG1-fAu0r4oeufQdw/view?usp=drive_link)
![Screenshot 2]([link-to-image](https://drive.google.com/file/d/1Jz1TFPNwI-dDc0o6QqBktmuCNoChnNAV/view?usp=drive_link)
![Screenshot 3]([link-to-image](https://drive.google.com/file/d/1KLzOqYqEiybCcm02pWho_upYZBg5EPSN/view?usp=drive_link)

## 💡 Inspiration
The inspiration for this project came from observing the operational inefficiencies in banking communication systems. We noticed that:

Banking staff spend 2-3 hours daily just sorting and routing emails
Customer response times suffer due to this manual bottleneck
Important requests sometimes get misclassified or overlooked
Different staff categorize similar requests inconsistently

We wanted to create a system that could think like an experienced banking operations specialist, understanding the nuanced differences between various request types while extracting critical information needed for processing.

## ⚙️ What It Does
Our system automatically:

Monitors bank email inboxes for new messages
Processes email content including text from attachments
Classifies emails into 12 distinct categories:

Adjustment
AU Transfer
Closing Notice
Commitment Change
Fee Payment
Money Movement-Inbound
Money Movement-Outbound
Inquiry
Complaint
Document Request
Account Maintenance
Security Concern


Extracts key information such as:

Loan numbers and account identifiers
Monetary amounts
Relevant dates
Contact information


Routes emails to appropriate teams using Gmail labels
Flags uncertain classifications for human review


## 🛠️ How We Built It
We built the system using n8n, a powerful workflow automation platform, with several key components:

Email Ingestion: Using n8n's IMAP trigger to monitor banking inboxes
Content Processing:

Parsing email bodies and extracting information
Processing attachments (including PDF text extraction)
Standardizing content for analysis


AI Classification:

Leveraging OpenAI's GPT-4 with specialized prompts
Custom context providing detailed banking request categories
Disambiguation rules for complex or overlapping requests


Data Extraction:

Pattern recognition for loan numbers, amounts, and dates
Structured data parsing for consistent output


Email Routing:

Gmail API integration for automatic labeling
Confidence-based routing logic
Separate workflows for high and low confidence classifications


## 🚧 Challenges We Faced
Building this system presented several significant challenges:

Classification Accuracy: Banking requests often overlap or contain multiple intents. We addressed this by developing a sophisticated prompt with detailed category definitions and disambiguation rules.
Attachment Processing: Extracting meaningful text from various attachment types required building specialized processing paths for different formats.
Gmail API Integration: We encountered challenges with message ID compatibility between IMAP and Gmail API. We solved this by implementing a search-based approach that finds messages based on sender and subject.
Handling Edge Cases: Emails with very low confidence scores or unusual request types needed special handling. We implemented a manual review routing system for these cases.
Maintaining Data Continuity: We had to ensure classification data persisted through multiple nodes, requiring careful data merging and preservation.

## 🏃 How to Run
To run this workflow, you'll need:

n8n instance (cloud or self-hosted)
Gmail account with API access
OpenAI API key

Setup steps:

Import the workflow JSON (code/Email_classification_IMAP_26_Mar.json) into your n8n instance
Configure the following credentials:

IMAP account for email reception
Gmail OAuth for labeling
OpenAI API for classification


Create Gmail labels for each classification category
Update label IDs in the Gmail nodes
Activate the workflow



## 🏗️ Tech Stack
Our solution leverages the following technologies:

n8n: Core workflow automation platform
OpenAI GPT-4: AI classification engine
Gmail API: Email labeling and routing
IMAP: Email reception
JavaScript: Custom processing logic in Code nodes
PDF.js: Attachment text extraction

## 👥 Team
- **Your Name** - [GitHub](#) | [LinkedIn](#)
- **Teammate 2** - [GitHub](#) | [LinkedIn](#)
