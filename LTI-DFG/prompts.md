# Prompts for Exercise

**Model Used:** Gemini 3 Pro (Preview)

---

## 📝 Prompt 1: Generate User Stories

**Role:** Expert Product Manager (ATS & Agile)

**Instruction:**
> You are an expert Product Manager with expertise in ATS and Agile methodologies.
>
> First, analyze the system described in `LTI-DFG/PRD.md`.
>
> **Task: Create user stories**
> Create at least 2 user stories for each user type for the system using the standard template:
> `As [user] I want [action] to [value given]`
>
> Be precise and do not include any information that is not requested.
> Ask any questions you need before making any decision.
>
> Add this to `UserStories-DFG.md`

---

## 📋 Prompt 2: Generate Backlog

**Role:** Expert Product Owner (ATS & Agile)

**Instruction:**
> You are an expert Product Owner with expertise in ATS and Agile methodologies.
>
> **Task: Create a product backlog**
>
> From the list of user stories described in `UserStories-DFG.md` create a product backlog with these considerations:
> - Give a Value score based on Fibonacci scale.
> - Consider dependencies between them.
> - Consider the completion of the full user flow between user types to give a release candidate version to them to be published as a package.
>
> Be precise and do not include any information that is not requested.
> Ask any questions you need before making any decision.
>
> Add this to `UserStories-DFG.md`

### 💡 Notes & Output
> *User Note:* Aquí me creó un product backlog que, aunque correcto, le faltaba mucho detalle. Además de 3 sprints un poco happy-flower :D

The following backlog is prioritized to deliver a complete "Release Candidate" flow, ensuring that a job can be created, approved, published, applied to, and interviewed for in a continuous cycle.

| Rank | ID | User Story | Value (Fibonacci) | Dependencies | Notes |
| :--- | :--- | :--- | :---: | :--- | :--- |
| 1 | **HM-1** | Approve Job Requisition | **5** | None | Prerequisite for publishing. Ensures budget alignment. |
| 2 | **REC-1** | Publish Job to Channels | **13** | HM-1 | Core feature. Brings traffic (candidates) to the system. |
| 3 | **CAND-1** | Resume Upload & Pre-fill | **21** | REC-1 | Critical entry point. High value for user acquisition. |
| 4 | **REC-2** | Candidate Notifications | **5** | CAND-1 | Keeps the process moving fast. |
| 5 | **HM-2** | Request Interview | **8** | CAND-1 | Moves candidate to the evaluation phase. |
| 6 | **CAND-2** | Self-Select Interview Slot | **8** | HM-2 | Solves the "scheduling nightmare" problem. |
| 7 | **INT-1** | View Interview Brief | **3** | CAND-2 | Ensures interview quality. |
| 8 | **INT-2** | Submit Scorecard | **8** | INT-1 | Captures the value of the interview for decision making. |

**Release Strategy:**
* **Sprint 1 (Foundation):** HM-1, REC-1, CAND-1. Goal: Get jobs live and collect applications.
* **Sprint 2 (Process):** HM-2, CAND-2, REC-2. Goal: Streamline the scheduling and notification loop.
* **Sprint 3 (Evaluation):** INT-1, INT-2. Goal: Enable structured decision making.

---

## 🚀 Prompt 3: Enrich User Stories

**Role:** Expert Product Owner & Business Analyst

**Instruction:**
> You are an expert Product Owner and Business analyst with expertise in ATS and Agile methodologies.
>
> From the given user stories in `LTI-DFG/UserStories.md`, enrich each story by including: detailed description, acceptance criteria, risks, dependencies, a Fibonacci value score, teams involved.
>
> Be precise and do not include any information that is not requested.
> Ask any questions you need before making any decision.

---

## 🗓️ Prompt 4: Create Detailed Backlog (Team & Capacity)

**Role:** Expert Product Owner (Software Startups)

**Instruction:**
> You are an expert Product Owner with expertise in software startups.
>
> Taking the user stories described in `LTI-DFG/UserStories.md` create a product backlog taking in account these considerations:
>
> - The team has 3 senior backend developers, 3 senior frontend developers, 1 senior UX designer, 1 junior UX designer, 2 senior software architects, 1 senior QA.
> - Sprint duration of 2 weeks.
> - Consider dependencies between teams while completing the user stories to maximize delivery.
> - Include release product candidates considering full completion of the business flow.
> - Assign effort estimation for each user story using fibonacci scale.
> - Sort the backlog considering high impact and dependencies.
>
> Be precise and do not include any information that is not requested.
> Ask any questions you need before making any decision.

---

## 🔨 Prompt 5: Create Tasks for Release 1 (CAND-1)

**Instruction:**
> From the user story CAND-1, create all the tasks for each team taking the capacity.
> Include for all of them:
>
> - title
> - type (feature, tech task, spike...)
> - purpose
> - detailed description of the task
> - acceptance criteria
> - validation checks
> - team assigned
> - sprint number
> - effort estimation in fibonacci scale for story points
> - dependencies of other tasks
> - related documentation
>
> Add this to `UserStories-DFG.md`

---

## 🎨 Prompt 6: Formatting & Visuals

**Instruction:**
> Add some emojis and better formatting to `file:UserStories-DFG.md` to provide better visual impact.
>
> Append to `UserStories-DFG.md` a table representing the sprint for the tasks in CAND-1.
