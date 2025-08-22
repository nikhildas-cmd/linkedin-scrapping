# 📊 Scrape LinkedIn Competitors’ Posts with n8n + Apify + Google Sheets

This workflow automates the process of **scraping LinkedIn posts from competitors or creators**, filtering by engagement (reposts > 20 in this case), and storing the results in **Google Sheets** for analysis.

---

## 🚀 How It Works

1. **Schedule Trigger / Manual Trigger**  
   - Runs weekly (or on-demand with manual trigger).  

2. **Google Sheets – Competitor List**  
   - Reads a list of competitor LinkedIn profile URLs from a Google Sheet.  

3. **Loop Over Items**  
   - Iterates over each LinkedIn profile.  

4. **Profile Scraping (Apify API)**  
   - Fetches recent posts, captions, engagement (likes, comments, reposts), and published date.  

5. **Filter**  
   - Only keeps posts with **more than 20 reposts** (can be customized).  

6. **Google Sheets – Save Results**  
   - Appends filtered posts into another sheet (`Linkedin Posts`) with details:  
     - Creator Name  
     - Post URL  
     - Caption/Text  
     - Likes  
     - Comments  
     - Reposts  
     - Published Date  

---

## 🔧 Tech Stack

- **n8n** → Workflow automation  
- **Google Sheets** → Competitor list + result storage  
- **Apify** → LinkedIn post scraper API  
- **Filter node** → Engagement-based filtering  

---

## 📂 Workflow Overview

```mermaid
flowchart TD
    A[Schedule/Manual Trigger] --> B[Google Sheets - Competitors]
    B --> C[Loop Over Competitors]
    C --> D[Apify Scraper - LinkedIn Posts]
    D --> E[Filter by Engagement]
    E --> F[Google Sheets - Save Results]
    F --> C
