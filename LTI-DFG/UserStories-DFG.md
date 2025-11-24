# 🌟 Enriched User Stories

## 🧑‍💼 1. Recruiter

### 📢 Story 1: Multi-Channel Job Publishing

**"As a Recruiter I want to create and publish a job opening to multiple channels simultaneously to reach a wider pool of candidates efficiently without manual duplication."**

* **📝 Description:** The recruiter needs a unified interface to input job details (title, description, requirements) once and push them to external job boards (LinkedIn, Indeed, Glassdoor) and the company career page via API integrations.
* **✅ Acceptance Criteria:**
  * User can select multiple destination channels (e.g., LinkedIn, Indeed) from a checklist.
  * System validates job data against specific requirements of selected boards.
  * User receives a confirmation link/status for each posted job.
  * Job status updates to "Published" in the internal dashboard.
* **⚠️ Risks:** API rate limits or changes in third-party job board schemas; authentication failures.
* **🔗 Dependencies:** HM-1 (Job Requisition Approval).
* **🔢 Value Score:** 13
* **👥 Teams Involved:** Backend, Frontend, Integrations.

### 🔔 Story 2: Automated Candidate Notifications

**"As a Recruiter I want to receive automated notifications about new qualified candidates to quickly identify and engage with top talent before competitors do."**

* **📝 Description:** The system monitors incoming applications and triggers an alert (email or in-app) to the recruiter when a candidate's AI matching score exceeds a defined threshold.
* **✅ Acceptance Criteria:**
  * Notification triggers only for candidates with a match score > 80% (configurable).
  * Notification includes candidate name, role applied for, and match score.
  * Clicking the notification navigates directly to the candidate's profile.
* **⚠️ Risks:** Notification fatigue if thresholds are too low; false positives from AI scoring.
* **🔗 Dependencies:** CAND-1 (Resume Parsing & Scoring).
* **🔢 Value Score:** 5
* **👥 Teams Involved:** Backend, Notification Service, AI/ML.

---

## 🤝 2. Hiring Manager

### ✅ Story 3: Approve Job Requisition

**"As a Hiring Manager I want to approve job requisitions submitted by recruiters to ensure that the open roles align with my team's strategic needs and budget."**

* **📝 Description:** A workflow step where the Hiring Manager reviews the draft job description, salary range, and department allocation before the job can be made public.
* **✅ Acceptance Criteria:**
  * HM receives an email request for approval with a link to the draft.
  * HM can "Approve" or "Reject" the requisition.
  * If rejected, HM must provide a comment explaining the reason.
  * Job status updates to "Open" immediately upon approval.
* **⚠️ Risks:** Process bottleneck if HM is unresponsive; lack of clear budget data in the view.
* **🔗 Dependencies:** None.
* **🔢 Value Score:** 5
* **👥 Teams Involved:** Backend, Frontend.

### 📅 Story 4: Request Interview

**"As a Hiring Manager I want to request an interview with a specific candidate directly in the system to move them to the next stage of the hiring process without email delays."**

* **📝 Description:** The HM selects a candidate from the pipeline and initiates the interview scheduling workflow, specifying the interview type and preferred time windows or interviewers.
* **✅ Acceptance Criteria:**
  * HM can select interview type (e.g., Screening, Technical, Cultural).
  * HM can assign specific interviewers to the request.
  * Candidate status changes to "Interview Requested".
  * System triggers the scheduling email to the candidate (linked to CAND-2).
* **⚠️ Risks:** Selected interviewers having no availability; calendar integration failures.
* **🔗 Dependencies:** CAND-1 (Candidate profile exists).
* **🔢 Value Score:** 8
* **👥 Teams Involved:** Backend, Frontend.

---

## 🙋 3. Candidate

### 📄 Story 5: Resume Upload & Pre-fill

**"As a Candidate I want to upload my resume and have my application form pre-filled to save time and reduce friction during the application process."**

* **📝 Description:** When applying, the candidate uploads a resume file (PDF/Docx). The system parses the file using AI/OCR to extract contact info, work history, and skills, populating the application fields automatically.
* **✅ Acceptance Criteria:**
  * System accepts PDF and DOCX formats up to 5MB.
  * Parsing correctly extracts Name, Email, Phone, and Skills with >90% accuracy.
  * Candidate can review and manually edit any pre-filled field before submission.
  * System provides immediate feedback on upload errors (e.g., file corrupted).
* **⚠️ Risks:** Parsing failure for complex or creative resume layouts; data privacy concerns with AI processing.
* **🔗 Dependencies:** REC-1 (Job must exist to apply to).
* **🔢 Value Score:** 21
* **👥 Teams Involved:** AI/ML, Backend, Frontend.

### 🗓️ Story 6: Self-Select Interview Slot

**"As a Candidate I want to self-select an interview time slot from a list of available options to avoid the back-and-forth email tag of scheduling."**

* **📝 Description:** The candidate receives a unique link to a scheduling portal where they see real-time availability of the interviewers and can book a slot that works for them.
* **✅ Acceptance Criteria:**
  * Candidate sees only available slots (based on interviewer calendar sync).
  * Time slots are displayed in the candidate's local timezone.
  * Selecting a slot automatically books the meeting and sends calendar invites to both parties.
  * Link expires after a set period (e.g., 48 hours).
* **⚠️ Risks:** Timezone conversion errors; double-booking if calendar sync lags.
* **🔗 Dependencies:** HM-2 (Interview requested).
* **🔢 Value Score:** 8
* **👥 Teams Involved:** Backend, Frontend, Integrations (Calendar).

---

## 📝 4. Interviewer

### 📋 Story 7: View Interview Brief

**"As an Interviewer I want to view the interview brief and candidate profile before the meeting to be well-prepared and conduct a focused, effective assessment."**

* **📝 Description:** The interviewer accesses a dedicated page containing the candidate's resume, the job description, and a specific list of competencies or questions to cover during the session.
* **✅ Acceptance Criteria:**
  * Brief is accessible via a secure link in the calendar invite.
  * Page displays Candidate Resume (view only), Job Description, and Competency Checklist.
  * Access is restricted to the assigned interviewer and hiring team.
* **⚠️ Risks:** Interviewer not checking the brief in time; permissions issues preventing access.
* **🔗 Dependencies:** CAND-2 (Interview scheduled).
* **🔢 Value Score:** 3
* **👥 Teams Involved:** Frontend, Backend.

### 📊 Story 8: Submit Scorecard

**"As an Interviewer I want to submit a structured scorecard immediately after the interview to provide timely, objective feedback that speeds up the hiring decision."**

* **📝 Description:** A digital form where the interviewer rates the candidate on specific competencies defined in the brief and provides a final recommendation (Hire/No Hire).
* **✅ Acceptance Criteria:**
  * Scorecard includes a 1-5 rating scale for each assigned competency.
  * "No Hire" recommendation requires a mandatory text explanation.
  * Submitting the scorecard updates the candidate's record and notifies the Recruiter/HM.
  * Drafts are auto-saved if the browser closes.
* **⚠️ Risks:** Subjective bias in ratings; delayed submission holding up the process.
* **🔗 Dependencies:** INT-1 (Brief/Interview context).
* **🔢 Value Score:** 8
* **👥 Teams Involved:** Backend, Frontend.

---

# 🗓️ Product Backlog

## 👥 Team Configuration & Capacity

* **💻 Development:** 3 Backend (Sen), 3 Frontend (Sen), 2 Architects (Sen).
* **🎨 Design/UX:** 1 Senior, 1 Junior.
* **🧪 QA:** 1 Senior.
* **⏱️ Sprint Duration:** 2 Weeks.

## 🎯 Prioritization Strategy

The backlog is ordered to unlock the **Critical Path** first: *Job Creation -> Application -> Interview -> Decision*.
High-complexity integration tasks (Job Boards, AI Parsing, Calendar Sync) are front-loaded to leverage the Senior Architects early.

---

## 🚀 Release 1.0: Talent Acquisition Core (Sourcing & Applying)

**🎯 Goal:** Enable the company to post jobs and receive applications. This is the MVP for data entry.

| Rank | ID | Story Name | Effort (Fib) | Priority | Dependencies | Teams Involved |
| :--- | :--- | :--- | :---: | :---: | :--- | :--- |
| 1 | **HM-1** | Approve Job Requisition | **3** | 🔴 High | None | UX, FE, BE |
| 2 | **REC-1** | Multi-Channel Job Publishing | **13** | 🔴 High | HM-1 | Arch, BE, FE, QA |
| 3 | **CAND-1** | Resume Upload & Pre-fill | **13** | 🔴 High | REC-1 | Arch (AI), BE, FE, UX |

* **🔢 Total Effort:** 29 Points.
* **💡 Rationale:** HM-1 is the prerequisite. REC-1 and CAND-1 are technically heavy (Integrations & AI) but essential for the "Sourcing" value proposition. Architects will focus heavily here.

---

## 🤖 Release 1.1: Engagement Automation (Scheduling & Comms)

**🎯 Goal:** Remove the manual bottleneck of scheduling and notifying, increasing process velocity.

| Rank | ID | Story Name | Effort (Fib) | Priority | Dependencies | Teams Involved |
| :--- | :--- | :--- | :---: | :---: | :--- | :--- |
| 4 | **REC-2** | Automated Candidate Notifications | **5** | 🟡 Medium | CAND-1 | BE, QA |
| 5 | **HM-2** | Request Interview | **5** | 🔴 High | CAND-1 | UX, FE, BE |
| 6 | **CAND-2** | Self-Select Interview Slot | **13** | 🔴 High | HM-2 | Arch (Cal), BE, FE, UX |

* **🔢 Total Effort:** 23 Points.
* **💡 Rationale:** CAND-2 is the complex piece here (Calendar Sync). REC-2 and HM-2 are standard workflow features. This release completes the "Logistics" loop.

---

## ⚖️ Release 1.2: Assessment & Decision (Interviewing)

**🎯 Goal:** Standardize the evaluation process to ensure quality hires.

| Rank | ID | Story Name | Effort (Fib) | Priority | Dependencies | Teams Involved |
| :--- | :--- | :--- | :---: | :---: | :--- | :--- |
| 7 | **INT-1** | View Interview Brief | **3** | 🟡 Medium | CAND-2 | FE, BE |
| 8 | **INT-2** | Submit Scorecard | **5** | 🔴 High | INT-1 | UX, FE, BE, QA |

* **🔢 Total Effort:** 8 Points.
* **💡 Rationale:** Lower technical complexity. Focus is on UX and data capture. Allows capacity for bug fixing and polish of previous releases.

---

## 📊 Summary of Effort

* **🔢 Total Story Points:** 60
* **🏃 Estimated Sprints:** 3 (assuming ~25-30 points velocity per sprint with this senior-heavy team).

---

# 🔨 Tasks for User Story CAND-1: Resume Upload & Pre-fill

**Parent Story:** CAND-1 (Resume Upload & Pre-fill)
**Sprint:** 1
**Total Story Points:** 13

---

## 🏗️ 1. Architecture & AI

### 📐 Task 1.1: Design Resume Parsing Pipeline

* **🏷️ Title:** Design Resume Parsing Pipeline Architecture
* **📌 Type:** Spike / Tech Task
* **🎯 Purpose:** To define the event-driven flow for processing uploaded resumes without blocking the UI.
* **📝 Detailed Description:** Design the AWS architecture using S3 (upload trigger), Lambda (orchestrator), and Textract/Bedrock (AI processing). Define the JSON schema for the parsed output (Contact Info, Skills, Experience).
* **✅ Acceptance Criteria:**
  * Architecture diagram approved by Lead Architect.
  * JSON Schema for "ParsedCandidateProfile" defined and documented.
  * Selection of AI model (Textract vs Bedrock) finalized based on cost/accuracy.
* **🔍 Validation Checks:** Review against AWS best practices for serverless scalability.
* **👥 Team Assigned:** Architecture (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 3
* **🔗 Dependencies:** None
* **📚 Related Documentation:** PRD Section 8 (System Architecture).

---

## ⚙️ 2. Backend Development

### 📤 Task 2.1: Implement S3 Presigned URL Endpoint

* **🏷️ Title:** Create API for Secure Resume Upload
* **📌 Type:** Feature
* **🎯 Purpose:** To allow the frontend to upload files directly to S3 securely.
* **📝 Detailed Description:** Develop a Lambda function exposed via API Gateway that generates a presigned S3 URL. The endpoint must validate file type (PDF/DOCX) and size (<5MB) before generating the link.
* **✅ Acceptance Criteria:**
  * `POST /upload-url` returns a valid S3 presigned URL.
  * Rejects non-PDF/DOCX files.
  * Rejects files > 5MB.
* **🔍 Validation Checks:** Unit tests for file validation logic; Integration test with S3.
* **👥 Team Assigned:** Backend (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 2
* **🔗 Dependencies:** Task 1.1 (Architecture decision on bucket structure).
* **📚 Related Documentation:** AWS S3 Presigned URLs docs.

### 🧠 Task 2.2: Develop Resume Parsing Lambda

* **🏷️ Title:** Implement Resume Parsing Logic
* **📌 Type:** Feature
* **🎯 Purpose:** To extract structured data from the raw file.
* **📝 Detailed Description:** Create a Lambda function triggered by S3 `ObjectCreated`. It should call the AI service (Textract/Bedrock), map the output to the `ParsedCandidateProfile` schema, and save the result to the `Candidate` database table.
* **✅ Acceptance Criteria:**
  * Lambda triggers successfully on file upload.
  * Extracts Name, Email, Phone, and Skills correctly.
  * Saves structured data to PostgreSQL.
  * Handles errors (e.g., unreadable PDF) gracefully.
* **🔍 Validation Checks:** Test with sample resumes (standard and complex layouts).
* **👥 Team Assigned:** Backend (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 5
* **🔗 Dependencies:** Task 1.1 (Schema), Task 2.1 (Upload flow).
* **📚 Related Documentation:** JSON Schema from Task 1.1.

---

## 🎨 3. Frontend Development

### 🖱️ Task 3.1: Build File Upload Component

* **🏷️ Title:** Develop Drag-and-Drop Upload UI
* **📌 Type:** Feature
* **🎯 Purpose:** To provide a user-friendly interface for candidates to submit their CVs.
* **📝 Detailed Description:** Create a React component that supports drag-and-drop. It should call the backend to get the presigned URL and then upload the file directly to S3. Show progress bars and error states.
* **✅ Acceptance Criteria:**
  * Supports Drag & Drop and "Browse" file selection.
  * Validates file type/size client-side before request.
  * Shows upload progress percentage.
  * Displays success/error messages clearly.
* **🔍 Validation Checks:** Cross-browser testing (Chrome, Safari, Firefox).
* **👥 Team Assigned:** Frontend (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 3
* **🔗 Dependencies:** Task 2.1 (API Endpoint).
* **📚 Related Documentation:** Figma Designs (Mockups).

### 📝 Task 3.2: Create Application Form with Pre-fill Logic

* **🏷️ Title:** Implement Dynamic Application Form
* **📌 Type:** Feature
* **🎯 Purpose:** To display the parsed data to the user for verification.
* **📝 Detailed Description:** Build the form that displays the candidate's profile. Implement a polling mechanism (or WebSocket subscription) to listen for the "Parsing Complete" event and auto-populate the form fields (Name, Email, Skills) once the backend finishes processing.
* **✅ Acceptance Criteria:**
  * Form fields are editable by the user.
  * Auto-populates data when parsing is done.
  * "Submit" button saves the final verified data.
* **🔍 Validation Checks:** Verify data binding works correctly; ensure no data loss on refresh.
* **👥 Team Assigned:** Frontend (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 5
* **🔗 Dependencies:** Task 2.2 (Parsing Logic), Task 3.1 (Upload UI).
* **📚 Related Documentation:** Figma Designs.

---

## 🖌️ 4. UX/UI Design

### 🎭 Task 4.1: Design Application Flow & Feedback States

* **🏷️ Title:** Design Upload & Parsing Experience
* **📌 Type:** Design Task
* **🎯 Purpose:** To ensure the user understands what is happening during the "AI Processing" wait time.
* **📝 Detailed Description:** Create high-fidelity mockups for the upload state, the "Analyzing your resume..." loading state, and the final pre-filled form. Define error messages for failed parses.
* **✅ Acceptance Criteria:**
  * Figma prototypes for happy and error paths.
  * Loading animations defined.
  * Mobile responsive layout designed.
* **🔍 Validation Checks:** Design review with Product Owner.
* **👥 Team Assigned:** UX Designer (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 2
* **🔗 Dependencies:** None.
* **📚 Related Documentation:** Brand Guidelines.

---

## 🧪 5. QA

### 🕵️ Task 5.1: Test Resume Parsing Accuracy

* **🏷️ Title:** Validate AI Parsing Accuracy
* **📌 Type:** QA Task
* **🎯 Purpose:** To ensure the AI model meets the >90% accuracy requirement.
* **📝 Detailed Description:** Create a test suite of 50 diverse resumes (different formats, layouts, languages). Run them through the pipeline and verify the extracted data against the ground truth.
* **✅ Acceptance Criteria:**
  * Test report showing success rate per field (Name, Email, Skills).
  * Identification of edge cases where parsing fails.
* **🔍 Validation Checks:** Manual verification of database records vs source files.
* **👥 Team Assigned:** QA (Senior)
* **⏱️ Sprint:** 1
* **🔢 Effort:** 3
* **🔗 Dependencies:** Task 2.2 (Parsing Lambda).
* **📚 Related Documentation:** Test Plan.

---

## 🏃 Sprint 1 Planning: CAND-1

| Task ID | Title | Team | Effort | Sprint |
| :--- | :--- | :--- | :---: | :---: |
| **1.1** | Design Resume Parsing Pipeline | Architecture | 3 | 1 |
| **2.1** | Implement S3 Presigned URL Endpoint | Backend | 2 | 1 |
| **2.2** | Develop Resume Parsing Lambda | Backend | 5 | 1 |
| **3.1** | Build File Upload Component | Frontend | 3 | 1 |
| **3.2** | Create Application Form with Pre-fill Logic | Frontend | 5 | 1 |
| **4.1** | Design Application Flow & Feedback States | UX/UI | 2 | 1 |
| **5.1** | Test Resume Parsing Accuracy | QA | 3 | 1 |
| **TOTAL** | | | **23** | |

