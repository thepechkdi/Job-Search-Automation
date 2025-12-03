# Structure Resume Prompt

You are an AI assistant. Your task is to convert the candidate’s raw resume text into clean, structured JSON.

Return ONLY this JSON format:

{
  "name": "",
  "email": "",
  "phone": "",
  "location": "",
  "skills": [],
  "experience": [
    {
      "company": "",
      "position": "",
      "start_date": "",
      "end_date": "",
      "description": ""
    }
  ],
  "education": [
    {
      "degree": "",
      "school": "",
      "year": ""
    }
  ],
  "links": {
    "linkedin": "",
    "github": ""
  }
}

Rules:
- Extract all relevant skills, including technical and soft skills.
- Summaries and descriptions must be concise and factual.
- If information is missing, leave fields empty.
