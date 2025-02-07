# sentence_constructor

the prompt is inserted inside the languagge file. Each language as this default prompt updated to the language (is french the prompt will be in french)

## Below the prompt

As a recruiter, I am looking to determine whether the job description aligns with the competencies listed in the resume.
Here are the competencies and scores from the resume that need to be analyzed in the job description: {{skills_data}}.
Here is the job description: {{job_description}}.

I am consulting three experts to discuss the job description during a roundtable discussion, attempting to solve the question step by step and ensuring the result is correct to avoid any errors.
The experts must consider the context (industry, department, etc.) of both the job description and the resume to provide the most accurate evaluation possible.

Guidelines:
    - The higher the skill score, the more attention should be paid to the job description to compare the candidate's knowledge with the requirements of the role.
    Assign a new score from 0 to 5 for each skill based on its relevance to the job description.
    - If the skill does not exist, assign a score of 0, unless the job description context suggests that the candidate might possess related skills. In that case, lower the score accordingly.
    - Include a brief comment on the analysis.
    - Ensure that the assigned score aligns with the comment; if not, adjust accordingly.

Here are examples of the expected results:


    **Expected output format (JSON only):**
```json
{
  "skills_evaluation": [
    {
      "skill": "Collaboration",
      "score": "4/5",
      "comment": "The candidate has significant skills for the role, hence the score of 4/5."
    },
    {
      "skill": "Quantitative analysis",
      "score": "3/5",
      "comment": "The candidate's knowledge needs improvement, leading to a reduced score of 3/5."
    },
    {
      "skill": "AZURE",
      "score": "2/5",
      "comment": "Cloud skills are mentioned, but the job description does not specify detailed Azure expertise, leading to a reduced score."
    }
  ]
}


Result to provide :
   - Translate into French.
   - Review the analysis with a critical approach and fill in any missing points.
   - "score" must always be in lowercase.
   - Provide only the results and remove all prompt messages.
   - provide the raw analysis results under json format

