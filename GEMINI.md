# CV Generation and Application Tracking Hub

This repository provides a structured system for managing professional experience, generating tailored CVs, and tracking job applications.

## Repository Workflow

This repository is your central hub for managing your professional story.

### 1. Store Raw Experience

Individual experience files are stored in the `experiences/` directory. Each `exp_*.md` file represents a distinct chapter of your career (e.g., a job, degree, or major project). These are the raw, detailed building blocks for your CVs.

Keep them rich with detail. When you have a new achievement, add it to the relevant file following the template below.

### 2. Build Master CVs

The `/masters` directory holds "master" versions of your CV, tailored for different role types (e.g., `applied_ml_scientist.md`, `ml_engineer.md`).

These high-level CVs should be assembled by picking the *most relevant* bullet points from your various `experiences/exp_*.md` files for a specific type of role.

### 3. Track Applications

When you apply for a job, create a dedicated folder in the `/applications` directory to track it. This creates a valuable log of your job search.

*   **Folder Name:** `YYYY-MM-DD_CompanyName_RoleTitle` (e.g., `2026-01-25_Google_ML-Engineer`)
*   **Contents:**
    *   `job_description.md`: The original job description.
    *   `cv_submitted.pdf`: The exact CV version you submitted.
    *   `notes.md`: Your notes on the process, interviews, and outcomes.

### 4. Importing Content from External CVs

To efficiently integrate existing CV content (e.g., from `.docx` or `.pdf` files) into your structured `experiences/` files, follow these steps:

1.  **Convert to Plain Text:** Open your external CV document and copy its entire text content. If possible, convert the document to a plain text file (`.txt`) to avoid formatting issues.
2.  **Provide Text to Agent:** When prompted by the agent, paste the plain text content directly into the chat. The agent will then process this text.
3.  **Agent Integration:** The agent will use the provided text to help integrate relevant achievements and details into your `experiences/exp_*.md` files, ensuring adherence to the "Experience File Template."

---

## Typical Workflows

This section outlines common tasks and best practices for managing your professional narrative within this repository.

### 1. Adding a New Job Achievement

To keep your experience files up-to-date, follow these steps:

1.  **Identify the relevant experience file:** Locate the `exp_*.md` file in the `experiences/` directory that corresponds to the job or project where you gained the new achievement.
    *   *Example:* If the achievement is from your CSIRO work, edit `experiences/exp_csiro.md`.
2.  **Edit the file:** Open the identified Markdown file in your editor.
3.  **Add a new "Project or Achievement" section:** Follow the "Experience File Template" below. Ensure you:
    *   Clearly state the **Objective**.
    *   Detail the **Engineering / Technologies** used, bolding key skills and quantifying your contributions.
    *   Articulate the **Impact** of your work, focusing on value created.

    ```bash
    # Example: Open CSIRO experience file to add a new achievement
    edit experiences/exp_csiro.md
    ```

### 2. Generating a New CV for an Application

When applying for a specific job, you'll tailor a CV from your master versions and raw experiences:

1.  **Create an application directory:** Make a new folder in `applications/` for the specific role.
    *   *Example:* `mkdir applications/2026-03-01_AwesomeCompany_ML-Engineer`
2.  **Save the job description:** Copy the job description into `job_description.md` within the new application directory.
    *   *Example:* `write_file applications/2026-03-01_AwesomeCompany_ML-Engineer/job_description.md "..."`
3.  **Select/Create a master CV:**
    *   Start with a relevant master CV from the `masters/` directory (e.g., `masters/applied_ml_scientist.md`).
    *   **OR:** If no existing master CV fits, create a new one in the `masters/` directory first.
    *   *Example:* `cp masters/applied_ml_scientist.md applications/2026-03-01_AwesomeCompany_ML-Engineer/cv_draft.md`
4.  **Tailor the CV:** Open `cv_draft.md` (or your chosen master CV) and customize it:
    *   **Review the `job_description.md`:** Identify keywords, required skills, and responsibilities.
    *   **Pull relevant bullets:** Go through your `experiences/exp_*.md` files. Select the most pertinent bullet points and integrate them into your `cv_draft.md`, adjusting wording to align with the job description.
    *   **Adjust summary/skills:** Ensure your CV summary and skills section highlight what's most relevant to the role.
5.  **Finalize and save:** Convert your tailored `cv_draft.md` into a PDF (if required) and save it as `cv_submitted.pdf` in the application directory.
    *   *Example:* (Assuming you have a tool to convert markdown to PDF) `markdown-to-pdf applications/2026-03-01_AwesomeCompany_ML-Engineer/cv_draft.md -o applications/2026-03-01_AwesomeCompany_ML-Engineer/cv_submitted.pdf`
6.  **Add notes:** Use `notes.md` to record any specific details, interview stages, or personal reflections related to this application.
    *   *Example:* `edit applications/2026-03-01_AwesomeCompany_ML-Engineer/notes.md`

---

All experience files should follow the structure below to ensure they can be easily parsed and reused.

````markdown
---
title: "Your Role Title"
company: "Company/University/Organization"
period: "YYYY - YYYY"
location: "City, Country"
---

### 1. Project or Achievement Name

*   **Objective:** State the high-level goal. What was the business or research problem you were trying to solve?
*   **Engineering / Technologies:**
    *   List the specific actions you took. Use strong verbs.
    *   Bold the **key technologies**, frameworks, and methodologies you used (e.g., **Python**, **PyTorch**, **HPC**, **CI/CD**, **Docker**, **FastAPI**).
    *   Quantify the scale of your work whenever possible (e.g., "processed 10TB of data," "handled 100,000 simulations," "improved performance by 30%").
*   **Impact:**
    *   What was the outcome? How did your work create value?
    *   Mention publications, operational improvements, or new capabilities enabled by your work. Connect it to business or research goals.

### 2. Second Project or Achievement...
````
