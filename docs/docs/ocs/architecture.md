# System Architecture

## Components
1. **Automation Workflow Engine**
   Orchestrates job fetching, skill matching, and document creation.

2. **OpenAI (GPT-4o / GPT-4o-mini / GPT-4o-latest)**
   - Structures CV data
   - Extracts job info
   - Produces JSON metadata
   - Generates tailored cover letters

3. **Google Sheets**
   Stores:
   - Job metadata
   - Skill match score
   - Cover letter
   - Application tracking

4. **Hash & Cache System**
   Prevents processing the same job more than once.

---

## High-Level Architecture Diagram (Text Version)

