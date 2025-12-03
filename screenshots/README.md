# Workflow Overview Screenshot

This screenshot shows the complete Job Search Automation workflow built in n8n.
It illustrates how the system automatically processes job postings, extracts structured data, matches the job with the user's resume, generates tailored cover letters, and updates Google Sheets — all without manual effort.

What the Workflow Does (shown in the image)

Fetch LinkedIn job postings via RSS

Extract job details (title, skills, requirements, company info)

Prevent duplicates using caching & hashing logic

Parse resume data into structured JSON

Match skills between resume and job

Generate a custom cover letter using OpenAI

Save results to Google Sheets

Maintain history in the resume/job cache

This visual representation helps developers understand the automation pipeline and how each component connects.
