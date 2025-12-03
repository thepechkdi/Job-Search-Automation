# 🤖 LinkedIn-Job-Automation

Automate your entire job application pipeline using **Automation + OpenAI + Google Sheets**.  
From collecting job posts → matching your skills → generating a cover letter → saving everything in a sheet.

---

## 🧩 Overview

This project is a fully automated workflow that:

- Finds job offers from **LinkedIn (RSS)**  
- Reads and structures your **resume (CV)**  
- Compares job requirements with your skills  
- Generates a **personalized cover letter**  
- Updates a **Google Sheet** with all results

Built as part of my AI & automation learning journey at **ISMONCTIC - MA**.

---

## 🎯 Project Goals

- Save time on repetitive job applications  
- Get **consistent & high-quality** cover letters  
- Keep an organized history of all applications  
- Practice real-world **AI Agents + Automation + APIs**

---

## ⚙️ Main Features

- 🔎 **Job scraping** via LinkedIn RSS feed  
- 📄 **Resume structuring** with OpenAI  
- 🧠 **Skill match analysis** (matching & missing skills)  
- 📝 **One-page cover letter** auto-generated for each job  
- 📊 **Google Sheets sync** (job details, match score, cover letter)  
- 🔁 **Caching** to avoid re-processing the same CV  

---

## 🧱 Architecture & Workflow

1. **Generate Hash (Caching)**  
   - Creates a unique hash from your resume content  
   - Used to check if the resume was already structured

2. **Loop Over Items**  
   - Processes each job posting one by one

3. **Structure Resume CV** (OpenAI)  
   - Converts raw CV text into JSON:
   - `skills`, `experience`, `education`, `projects`, etc.

4. **Merge Job + Resume**  
   - Combines:
     - `job` → job description, skills, company, location  
     - `resume` → structured CV  

5. **Create Match & Cover Letter** (OpenAI)  
   - Returns:
     - JSON with `matching_skills`, `missing_skills`, `summary`  
     - A professional one-page cover letter

6. **Update Row in Sheet**  
   - Writes:
     - Job ID  
     - Company name  
     - Position  
     - Skill match highlights  
     - Cover letter text  

---


## 💬 Author

Created by Ya Ha — student in Artificial Intelligence at ISMONTIC Tangier 🇲🇦



