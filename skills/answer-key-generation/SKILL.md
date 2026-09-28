---
name: answer-key-generation
description: Generate and iterate an answer key using available content, guiding a teacher or instructional leader through the process.
---

# Answer Key Generation

Use this skill when an OpenSciEd assessment Google Form is uploaded and the student instructions are available.

The goal is have a clear and concise answer key with the appropriate level of context that can be used by the teacher or instructional leader AND an LLM to evaluate student responses in the assessments.  

## Conversation style

- Lead the user through one phase at a time.
- Ask only for information needed for the current phase; make reasonable assumptions explicit.
- Preserve teacher control: offer options and tradeoffs, never prescribe an unverified schedule.
- State that the final plan is a draft to revisit as the year unfolds.

## The three phases

### Phase 1: Generate a starting answer key

Generate a draft answer key for the assessment based on the student instructions provided, and if an answer key is available. Ensure the number of questions match the answer key questions, and only retrieve answer keys for available questions. Use answer key text verbatim if answer key document is available to preserve fidelity. Add information of the NGSS standard the assessment is evaluating for. 

Also add supporting diagrams and images from the assessment's Google Form. Use URI to Eddo's Google Drive for the references, if available.

### Phase 2: Present the drafted answer key for teacher or instructional leader review 

Ask the user if the answer key is sufficient for the assessment or more information need to be added. This is should be a loop, the updated answer key based on additional inputs is presented to the user until an answer key is sufficient.

If no rubric is available, craft a standard-based rubric write-up with four performance levels, "1 - Beginning", "2 - Approaching", "3 - Proficient", "4 - Extending" for the assessment and present it to the user. 

### Phase 3: Required final output

Generate the final answer key as markdown, to be downloadable. The answer key will have: 

- look-fors verbatim if answer key is provided, for each student instruction questions
- standard-based rubric, if user chose to provide
- Supporting text, diagrams and images

## Template

Use this structure:

```markdown
# Standard-based rubric

## Student instruction questions and the look-fors for each

## Support content
```
