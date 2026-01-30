# Research Protocol v1.0
**The Promptcraft Academy: A Randomized Controlled Evaluation of an AI Literacy Intervention**

## 1. Metadata
*   **Date Created:** 2026-01-30
*   **Protocol Version:** 1.0
*   **OSF Pre-Registration Link:** *[Link will be added after OSF registration]*

## 2. Introduction & Problem Statement
*(To be written: Brief on AI literacy gap, need for evidence-based training.)*

## 3. Hypotheses
1.  **H1 (Competency):** Students who complete the Promptcraft Academy intervention will demonstrate a significantly higher score on a practical AI task rubric than students in the control group.
2.  **H2 (Self-Efficacy):** The intervention group will show a greater increase in AI self-efficacy scores from pre-test to post-test compared to the control group.
3.  **H3 (Ethics):** The intervention group will demonstrate superior ability to identify ethical risks in AI use cases in a post-test scenario analysis.

## 4. Methodology
*(To be detailed: Participant recruitment, randomization, intervention description, control group protocol, blinding procedure.)*

### 4.1 Participant Recruitment & Sampling
We will recruit a convenience sample of **N = 60** undergraduate and graduate students from Óbuda University. Recruitment channels will include:
1.  University-wide mailing lists (with permission from department heads).
2.  Social media groups (Facebook, LinkedIn groups specific to ÓE students).
3.  Direct outreach to classroom instructors for in-class announcements.
4.  AI Squad and related tech club channels.

**Inclusion Criteria:**
*   Currently enrolled as a student at Óbuda University.
*   Has used at least one Generative AI tool (e.g., ChatGPT, DeepSeek, Perplexity Ai, Bohrium AI, Claude, Gemini, Copilot) at least once.
*   Provides informed digital consent.

**Exclusion Criteria:**
*   Participants who have completed formal university-level coursework or certification in Prompt Engineering or AI Ethics (to avoid prior-expertise bias).

### 4.2 Randomization & Group Assignment
Upon completion of the pre-test, each of the **N=60** participants will be assigned a unique, sequential Participant ID (PID: P001-P060). Using the `random.randint()` function in Python (or a verified online randomizer), we will generate a list of 30 random integers between 1 and 60. Participants whose PID corresponds to these numbers will be assigned to the **Intervention Group (IG, n=30)**. The remaining 30 participants will form the **Control Group (CG, n=30)**.

### 4.3 Intervention Protocol (Promptcraft Academy)
The Intervention Group will receive access to the **Promptcraft Academy**, a hosted, 4-module interactive cookbook. The intervention lasts **14 days**.

*   **Module 1: Foundations (Days 1-3):** LLM mechanics, basic prompt structure (Role-Context-Task-Format), token awareness.
*   **Module 2: Promptcraft (Days 4-7):** Advanced patterns (Chain-of-Thought, Persona, Criticism), iterative refinement.
*   **Module 3: Evaluation & Hallucination Mitigation (Days 8-10):** Cross-referencing outputs, critical reading, using AI to check AI.
*   **Module 4: Ethics & Application (Days 11-14):** Bias detection, citation, PII hygiene, academic integrity boundaries.

**Delivery:** Each module unlocks sequentially. Completion is tracked via embedded Google Form "checkpoints" at the end of each module. Participants must complete a module's checkpoint to unlock the next.

### 4.4 Control Group Protocol (Status Quo)
The Control Group will receive an email with a curated list of **5 high-quality, publicly available online resources** for learning about AI/prompt engineering. These will include:
1.  OpenAI's "Prompt Engineering Guide" (2023).
2.  DeepLearning.AI's "Short Course: ChatGPT Prompt Engineering for Developers".
3.  A selected YouTube playlist from a reputable AI educator (e.g., Andrew Ng).
4.  "Learn Prompting" website (Introduction section).
5.  A popular, highly-shared Medium article on "10 Useful ChatGPT Prompts."

They will be given the same 14-day period to engage with these materials *ad libitum*. This group represents the **current standard of self-directed learning** and serves as our active comparator.

### 4.5 Blinding & Procedure
This is a **single-blind study**. Participants will not be told their group assignment's label ("Intervention" vs. "Control"). They will be told they are participating in a study to "evaluate different AI learning resources."

**Scoring Blinding:** The primary outcome (Performance Task) will be scored by a research assistant who is **blinded to group assignment**. All submitted tasks will be anonymized (using PID) and randomized before scoring.

**Procedure Timeline:**
1.  **Day 0:** Recruitment closes, Pre-Test administered (Self-Efficacy Scale + Performance Task 1).
2.  **Day 1:** Randomization, Group assignment, Intervention/Control materials distributed.
3.  **Day 14:** Intervention period ends.
4.  **Day 15:** Post-Test administered (Self-Efficacy Scale + Performance Task 2 + Ethical Scenario).

This allocation sequence will be stored in a password-protected file, separate from the main participant data, to maintain allocation concealment until group assignment.

## 5. Measures
*(To be detailed: Description of Performance Task, Scoring Rubric, Self-Efficacy Scale, Ethical Scenario.)*
### 5.1 Primary Measure 1: AI Self-Efficacy Scale (AISES)
We developed a 10-item Likert-scale instrument (1-5) measuring confidence across practical AI tasks (summarization, brainstorming, debugging, persona use, data analysis, iterative refinement, hallucination detection, project planning, ethical use, and tool adaptability). **Internal consistency** will be assessed using Cronbach's Alpha. **Pre- and Post-Test scores** will be compared within and between groups.

*(See `self_efficacy_scale.md` for the full instrument.)*

### 5.2 Primary Measure 2: Performance Task Rubric
Participants complete a realistic AI task (summarizing a research abstract, extracting arguments, formulating critical questions). Performance is scored via a **12-point analytic rubric** across four dimensions: (A) Summary Accuracy, (B) Argument Extraction, (C) Prompt Sophistication, and (D) Ethical/Procedural Rigor.
Scoring will be performed by a blinded assessor. Inter-rater reliability will be established on a 20% sample (Cohen's Kappa). The rubric ensures objective, granular assessment beyond binary right/wrong.

*(See `performance_task_rubric.md` for the full task and rubric.)*

### 5.3 Secondary Measure: Ethical Scenario Analysis
In the post-test, both groups will analyze a short vignette:
*"A student uses an AI tool to generate the entire literature review section of their thesis. They edit the output slightly and submit it as their own work."*
They will be asked: **"Identify two distinct ethical or academic issues in this scenario and suggest a better, ethical alternative practice."**

Responses will be scored on a **0-2 scale** per issue (0=No/Misidentified issue, 1=Vague identification, 2=Clear identification with reasonable alternative).

## 6. Analysis Plan
*(To be detailed: Statistical tests for H1, H2, H3.)*
All analyses will be conducted in Python (using `pandas`, `scipy`, `scikit-posthocs`) or JASP, with an alpha level of .05.

1.   **Hypothesis 1 (Competency):** We will perform an **Independent Samples t-test** comparing the Post-Test Performance Task scores (out of 12) of the Intervention Group vs. the Control Group. We will also conduct a **2x2 Mixed ANOVA** (Time: Pre/Post × Group: IG/CG) to examine interaction effects.
2.   **Hypothesis 2 (Self-Efficacy):** We will perform a **Paired Samples t-test** on the AISES scores within the Intervention Group (Pre vs. Post). To compare the *change* between groups, we will calculate difference scores (Post-Pre) and run an Independent Samples t-test on these difference scores.
3.   **Hypothesis 3 (Ethics):** We will perform a **Mann-Whitney U test** (non-parametric) to compare the Ethical Scenario scores (ordinal data) between the Intervention and Control groups.
4.   **Exploratory Analysis:** We will analyze the correlation between Performance Task scores and Self-Efficacy scores. We will conduct a thematic analysis of the submitted prompts to categorize common strategies and pitfalls.

## 7. Project Timeline (Gantt)
| Week | Dates | Key Milestones |
|------|-------|----------------|
| 1 | 2026-01-30 to 2026-02-05 | Team formation, repo setup, protocol draft, OSF pre-reg. |
| 2 | 2026-02-06 to 2026-02-12 | Content design sprint, recruitment launch. |
| 3-4 | 2026-02-13 to 2026-02-26 | Cookbook development, finalize assessment tools. |
| 5-6 | 2026-02-27 to 2026-03-12 | Participant recruitment & pre-test administration. |
| 7-8 | 2026-03-13 to 2026-03-26 | Intervention delivery, post-test administration. |
| 9 | 2026-03-27 to 2026-04-02 | Data analysis & insight generation. |
| 10 | 2026-04-03 to 2026-04-09 | Deliverable assembly & final packaging. |
