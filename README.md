#AI-Powered LinkedIn Job Application Automation

Automate your entire job search using n8n, OpenAI, and Google Sheets.

This workflow collects job posts, analyzes them, matches skills with your resume, generates personalized cover letters, and updates a Google Sheet automatically — all without writing code.

📌 Features
✅ Automated Job Collection

Fetch LinkedIn job posts using RSS

Extract title, company, job description, skills, location

✅ Resume Parsing

Converts your resume into structured JSON

Extracts skills, experience, education, achievements

✅ Skill Matching

Returns JSON:

{
  "matching_skills": [],
  "missing_skills": [],
  "summary": ""
}

✅ AI-Generated Cover Letters

Creates a personalized, professional one-page cover letter using job + resume data.

✅ Google Sheets Integration

Automatically saves:

Job ID

Company

Matching skills

Skill match score

AI-generated cover letter

📂 Repository Structure
📁 docs/               → Documentation & architecture
📁 screenshots/        → Workflow screenshots
📁 prompts/            → OpenAI prompt templates
📁 workflow/           → n8n workflow JSON export
README.md              → Main documentation

🧠 Technologies Used
Tool	Purpose
n8n	Workflow automation
OpenAI (GPT-4o, GPT-4o-mini)	AI reasoning & cover letters
Google Sheets API	Saving job applications
LinkedIn RSS	Getting job listings
⚙️ Workflow Overview

Extract job postings

Parse resume using OpenAI

Merge job + resume

AI analyzes skills

AI generates cover letter

Google Sheets saves results

🧾 Main Prompt (Skill Match + Cover Letter)
You are a job application assistant.

You will be given structured data including:
- A job posting with its role description, requirements, skills, and company metadata.
- A candidate’s resume including skills, experience, and achievements.

Your task has two parts:

------------------------------------------------------------
1. Skill Match Evaluation

Return ONLY this JSON object:

{
  "matching_skills": [],
  "missing_skills": [],
  "summary": ""
}

matching_skills = skills appearing in both job.skills_and_tech and resume.skills.  
missing_skills = job-required skills missing from resume.  
summary = 3–4 sentences summarizing the match.

------------------------------------------------------------
2. Cover Letter Generation

Generate a tailored one-page cover letter.  
Must include:

[Your Name]  
[City, Country]  
[Email]  
[Phone]  

[Date]  
[Company Name]  
[Company Location]  

Dear Hiring Manager,  
(4 paragraphs…)  
Kind regards,  
[Your Name]

------------------------------------------------------------
INPUT DATA:

{
  "job": {{ $json["job"] }},
  "resume": {{ $json["resume"] }}
}

RULES:
- First output the JSON
- Then output the cover letter
- No code blocks
- No extra commentary

📝 Setup Instructions
Clone the repository
git clone https://github.com/thepechkdi/linkedin-job-automation.git

Launch n8n (Docker recommended)
docker run -it --rm -p 5678:5678 n8nio/n8n

Import workflow

Upload /workflow/job-automation.json inside n8n.

Add credentials

OpenAI API key

Google Sheets OAuth2

LinkedIn RSS source

📸 Screenshots

All screenshots are in /screenshots.

👨‍💻 Author

Yahya Hafid
AI Engineer & Automation Builder
🔗 https://www.linkedin.com/in/yahya-hafid
