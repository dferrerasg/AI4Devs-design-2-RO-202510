# 🚀 ATS Business Logic Overview

## 1. How an ATS Works

An **Applicant Tracking System (ATS)** is a software application that streamlines the recruitment process by automating job postings, resume screening, and interview scheduling. It serves as a central repository for candidate data, enabling HR teams to track applicants through various stages of the hiring pipeline—from application to offer—while facilitating collaboration among hiring managers.

```mermaid
sequenceDiagram
    participant R as Recruiter
    participant ATS as ATS System
    participant C as Candidate
    participant HM as Hiring Manager

    R->>ATS: Create & Publish Job
    ATS-->>C: Display Job Opening
    C->>ATS: Submit Application (Resume/Data)
    ATS->>ATS: Parse Resume & Auto-Screen
    ATS->>R: Notify of New Qualified Candidate
    R->>HM: Share Candidate Profile
    HM->>ATS: Request Interview
    ATS->>C: Send Scheduling Link
    C->>ATS: Select Time Slot
    ATS->>R: Confirm Interview
    HM->>ATS: Submit Interview Scorecard
    ATS->>C: Send Offer / Rejection
```

## 2. Main Functionalities

The following table outlines core functionalities. Features marked with a star (⭐) represent high-value areas for **automation, real-time collaboration, and AI assistance** to maximize efficiency.

| Functionality | Description | Efficiency Potential (⭐) |
| :--- | :--- | :---: |
| **Smart Resume Parsing** | Automatically extracting contact info, skills, and experience from CVs to populate profiles. | ⭐ |
| **AI-Driven Candidate Ranking** | Using AI to score and rank candidates based on job description relevance. | ⭐ |
| **Multi-Channel Job Posting** | One-click distribution of job openings to LinkedIn, Indeed, Glassdoor, etc. | ⭐ |
| **Automated Interview Scheduling** | Calendar integration allowing candidates to self-select available slots, reducing email tag. | ⭐ |
| **Collaborative Scorecards** | Real-time shared feedback forms for interviewers to rate candidates immediately. | ⭐ |
| **Automated Communication Workflows** | Trigger-based emails for application receipt, status updates, and rejections. | ⭐ |
| **Talent Pool CRM** | Searchable database of past applicants for future roles. | |
| **Diversity & Inclusion Analytics** | AI analysis of job descriptions and pipelines to ensure bias-free hiring. | ⭐ |
| **Offer Management** | Digital offer letter generation and e-signature integration. | |
| **Referral Portal** | Interface for employees to submit and track referrals. | |

## 3. Market Solutions Comparison

| Solution | Strengths | Weaknesses |
| :--- | :--- | :--- |
| **Greenhouse** | Industry standard for structured hiring; excellent reporting and DE&I tools; vast integration ecosystem. | Can be expensive for smaller startups; steep learning curve; UI can feel dense. |
| **Lever** | Strong CRM capabilities for sourcing passive candidates; intuitive and clean UI; great email integration. | Reporting is less granular than Greenhouse; can struggle with very high-volume hiring complexities. |
| **Workday** | Seamless integration with HRIS/Payroll (all-in-one); enterprise-grade security and compliance. | Clunky, outdated user experience; slow implementation; very expensive; not specialized for recruiting. |
| **Ashby** | Modern, fast UI; powerful custom analytics; combines ATS and CRM effectively; high automation capabilities. | Newer player with fewer legacy integrations; mobile experience is still maturing. |

## 4. Roadmap: Building the Next-Gen ATS

This roadmap focuses on the high-efficiency (⭐) features to build a competitive, automated, and intelligent system.

### **Phase 1: The Intelligent Core (Months 1-3)**

* **Goal:** Establish the data foundation and AI processing capabilities.
* **Features:**
  * Core Database & Candidate Profiles.
  * **Smart Resume Parsing (AI)**: Implement NLP to structure unstructured resume data.
  * **AI-Driven Candidate Ranking**: Develop matching algorithms to highlight top talent instantly.

### **Phase 2: Automation & Velocity (Months 4-6)**

* **Goal:** Remove manual administrative bottlenecks.
* **Features:**
  * **Automated Interview Scheduling**: Two-way calendar sync and self-scheduling portal.
  * **Multi-Channel Job Posting**: API integrations with major job boards.
  * **Automated Communication Workflows**: Set up state-change triggers for candidate emails.

### **Phase 3: Collaboration & Insights (Months 7-9)**

* **Goal:** Enhance team decision-making and process optimization.
* **Features:**
  * **Collaborative Scorecards**: Real-time syncing of interviewer feedback.
  * **Diversity & Inclusion Analytics**: Dashboards to monitor pipeline health and bias.
  * **AI Copilot for Recruiters**: Chat interface to query candidate data ("Show me Python devs in London").

## 5. Lean Canvas: ATS Business Logic

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| **PROBLEM**<br>1. Hiring takes too long (Time-to-Hire).<br>2. Good candidates are lost in black holes.<br>3. Scheduling interviews is a logistical nightmare.<br>4. Bias in screening processes. | **SOLUTION**<br>1. AI-powered screening to surface top talent fast.<br>2. Automated scheduling and communication loops.<br>3. Collaborative, structured hiring workflows.<br>4. Centralized candidate data. | **UNIQUE VALUE PROPOSITION**<br>"The first ATS that works for you, not against you."<br><br>An AI-native platform that automates 80% of admin work, allowing recruiters to focus on people, not spreadsheets. | **UNFAIR ADVANTAGE**<br>1. Proprietary matching algorithm.<br>2. Deep integration with developer tools (GitHub/StackOverflow) for tech hiring.<br>3. User-centric design (consumer-grade UX). | **CUSTOMER SEGMENTS**<br>1. High-growth Tech Startups (Series A-C).<br>2. Mid-market enterprises modernizing HR.<br>3. Recruitment Agencies.<br><br>**Early Adopters:**<br>Tech companies with remote-first hiring needs. |
| **EXISTING ALTERNATIVES**<br>1. Excel / Email (Manual).<br>2. Legacy Enterprise ATS (Workday, Taleo).<br>3. Modern ATS (Greenhouse, Lever). | **KEY METRICS**<br>1. Time-to-Hire (Days).<br>2. Candidate Net Promoter Score (cNPS).<br>3. Interview-to-Offer Ratio.<br>4. Admin hours saved per hire. | **CHANNELS**<br>1. Direct Sales / Demo requests.<br>2. Content Marketing (Hiring best practices).<br>3. Partnerships with HR consultancies.<br>4. Product-Led Growth (Free tier for small teams). | | |
| **COST STRUCTURE**<br>1. Cloud Infrastructure (AWS/Azure).<br>2. AI Model Training & API Costs.<br>3. Software Development Team.<br>4. Sales & Customer Success. | **REVENUE STREAMS**<br>1. SaaS Subscription (Per user or Per employee).<br>2. Enterprise Customization Fees.<br>3. Add-on features (Premium Job Board distribution). | | | |

## 6. Core Use Cases

### Use Case 1: Candidate Application Journey 📝
**Description:** The end-to-end process for a candidate to discover a job opening, submit their application, and receive confirmation. This is the "front door" of the ATS.

**Key Actors:**
*   **Candidate:** The job seeker.
*   **ATS System:** The platform handling the data.

**Success Metrics:**
*   **Application Completion Rate:** % of users who start and finish the application.
*   **Time-to-Apply:** Average time taken to complete the form (Target: < 5 mins).

**Risks:**
*   **High Drop-off Rate:** If the form is too long or requires account creation.
*   **Parsing Errors:** Resume parser failing to read non-standard formats.

```mermaid
sequenceDiagram
    actor C as Candidate
    participant ATS as ATS Portal
    participant DB as Database

    C->>ATS: Search/View Job Details
    C->>ATS: Click "Apply Now"
    ATS->>C: Request Resume Upload
    C->>ATS: Upload Resume (PDF/Docx)
    ATS->>ATS: Parse Resume Data (AI)
    ATS-->>C: Pre-fill Application Form
    C->>ATS: Review & Submit
    ATS->>DB: Save Application Record
    ATS-->>C: Send Confirmation Email
```

### Use Case 2: Job Creation & Publishing 📢
**Description:** The workflow for a recruiter or hiring manager to define a new role, get internal approval, and distribute it to external job boards.

**Key Actors:**
*   **Job Poster (Recruiter):** Initiates the process.
*   **Hiring Manager:** Approves the requisition.
*   **External Job Boards:** LinkedIn, Indeed, etc.

**Success Metrics:**
*   **Time-to-Publish:** Time from draft to live.
*   **Channel Reach:** Number of views/applications per channel.

**Risks:**
*   **Approval Bottlenecks:** Delays in internal sign-off.
*   **Integration Failures:** API errors preventing posting to external sites.

```mermaid
sequenceDiagram
    actor R as Recruiter
    actor HM as Hiring Manager
    participant ATS as ATS System
    participant Ext as Job Boards

    R->>ATS: Create Job Requisition
    ATS->>HM: Request Approval
    HM->>ATS: Approve Requisition
    ATS->>R: Notify Approval
    R->>ATS: Select Publishing Channels
    ATS->>Ext: Publish Job via API
    Ext-->>ATS: Confirm Posting URL
    ATS->>R: Dashboard Updated (Live)
```

### Use Case 3: Candidate Evaluation & Feedback ⚖️
**Description:** The process where an interviewer conducts the assessment and submits structured feedback to inform the hiring decision.

**Key Actors:**
*   **Interviewer:** Subject matter expert conducting the interview.
*   **Recruiter:** Coordinator of the process.

**Success Metrics:**
*   **Scorecard Submission Time:** Time between interview end and feedback submission (Target: < 24 hrs).
*   **Interviewer Calibration:** Consistency in scoring across different interviewers.

**Risks:**
*   **Unconscious Bias:** Subjective feedback affecting fairness.
*   **Delayed Feedback:** Slowing down the decision process, risking candidate loss.

```mermaid
sequenceDiagram
    actor I as Interviewer
    participant ATS as ATS System
    participant Cal as Calendar

    ATS->>I: Send Interview Invite & Brief
    I->>Cal: Accept Invite
    I->>ATS: Review Candidate Profile & Resume
    Note over I, ATS: Interview Takes Place
    I->>ATS: Open Scorecard Form
    I->>ATS: Rate Competencies & Add Notes
    I->>ATS: Submit Recommendation (Hire/No Hire)
    ATS->>ATS: Update Candidate Score
    ATS-->>I: Confirmation
```

## 7. Data Model 💾

This section outlines the core database schema required to support the ATS functionalities, focusing on the relationships between candidates, jobs, and the hiring workflow.

### **Entity Relationship Diagram (ERD)**

```mermaid
erDiagram
    User ||--o{ JobPosting : "manages"
    User ||--o{ InterviewParticipant : "attends"
    User ||--o{ Scorecard : "submits"
    
    JobPosting ||--o{ Application : "receives"
    Candidate ||--o{ Application : "submits"
    
    Application ||--o{ Interview : "has"
    Interview ||--o{ InterviewParticipant : "includes"
    Interview ||--o{ Scorecard : "results_in"

    User {
        uuid user_id PK
        string email
        string full_name
        enum role "RECRUITER, HIRING_MANAGER, INTERVIEWER"
    }

    JobPosting {
        uuid job_id PK
        string title
        text description
        string department
        enum status "DRAFT, OPEN, CLOSED"
        uuid hiring_manager_id FK
    }

    Candidate {
        uuid candidate_id PK
        string email
        string full_name
        string resume_url
        jsonb parsed_skills
    }

    Application {
        uuid application_id PK
        uuid job_id FK
        uuid candidate_id FK
        enum status "APPLIED, SCREENING, INTERVIEW, OFFER, REJECTED"
        float ai_match_score
        timestamp applied_at
    }

    Interview {
        uuid interview_id PK
        uuid application_id FK
        timestamp scheduled_at
        enum type "SCREENING, TECHNICAL, CULTURAL"
        string meeting_link
    }

    InterviewParticipant {
        uuid interview_id FK
        uuid user_id FK
    }

    Scorecard {
        uuid scorecard_id PK
        uuid interview_id FK
        uuid interviewer_id FK
        int rating "1-5"
        text feedback
        enum recommendation "HIRE, NO_HIRE"
    }
```

### **Entity Descriptions**

1.  **User**: Represents all internal system users.
    *   **Role**: Determines permissions (e.g., only Hiring Managers can approve Job Postings).
    *   **Relationships**: Can be a Hiring Manager for a Job, an Interviewer in an Interview, or the author of a Scorecard.

2.  **JobPosting**: A specific role opening.
    *   **Status**: Tracks the lifecycle of the opening (Draft -> Open -> Closed).
    *   **Hiring Manager**: The primary stakeholder responsible for the role.

3.  **Candidate**: The external applicant.
    *   **Parsed Skills**: JSON field storing skills extracted by AI from the resume for matching algorithms.
    *   **Resume URL**: Link to the stored document (e.g., S3 bucket).

4.  **Application**: The central entity linking a Candidate to a Job.
    *   **Status**: The most critical field, driving the Kanban board view (e.g., "Moved to Interview").
    *   **AI Match Score**: A calculated value (0-100) indicating fit, populated upon application submission.

5.  **Interview**: A scheduled event within an application process.
    *   **Type**: Distinguishes between phone screens, coding challenges, etc.
    *   **Participants**: Handled via a junction table (`InterviewParticipant`) to allow multiple interviewers (panel interviews).

6.  **Scorecard**: The structured feedback form.
    *   **Rating & Recommendation**: Quantitative data for reporting and decision support.
    *   **Link**: Directly tied to a specific Interview instance to track who said what and when.

## 8. System Architecture & Design 🏗️

### **Recommended Pattern: Event-Driven Serverless Architecture**

Based on the requirements for **AI processing** (resume parsing), **real-time collaboration** (scorecards), and **variable traffic loads** (job postings), an **Event-Driven Serverless** architecture is the most suitable choice.

**Why this choice?**
*   **Decoupling:** Heavy AI tasks (parsing resumes) won't block the user interface or the core API.
*   **Scalability:** Serverless functions (Lambda) scale automatically to handle bursts of applications without provisioning idle servers.
*   **Cost Efficiency:** You only pay for compute when code is running, which is ideal for an ATS where traffic fluctuates.

| Pros | Cons | Decision Rationale |
| :--- | :--- | :--- |
| **High Scalability:** Handles 1 or 10,000 applicants seamlessly. | **Cold Starts:** Slight latency for infrequently used functions. | Critical for "viral" job postings. |
| **Operational Simplicity:** No server patching or OS management. | **Vendor Lock-in:** Heavily tied to AWS ecosystem. | Accepted trade-off for development speed. |
| **Event Integration:** Native support for triggering AI workflows from file uploads. | **Debugging Complexity:** Distributed tracing can be harder. | Mitigated using AWS X-Ray. |

### **High-Level AWS System Design**

The system is composed of three main layers: **Frontend (Client)**, **Backend (API & Logic)**, and **Data/AI Layer**.

1.  **Frontend (SPA)**
    *   **Hosting:** **AWS Amplify** (or S3 + CloudFront) for hosting the React/Next.js application.
    *   **Authentication:** **Amazon Cognito** for user management (Recruiters, Candidates) and JWT token generation.

2.  **Backend (API & Compute)**
    *   **API Gateway:** Entry point for all RESTful requests.
    *   **AWS Lambda:** Serverless compute for business logic (CRUD operations, status updates).
    *   **AWS AppSync (GraphQL):** Used specifically for **Real-Time Collaboration** on Scorecards, allowing interviewers to see updates instantly.

3.  **Asynchronous & AI Workflows**
    *   **Amazon EventBridge:** The central event bus. When a candidate applies, an event is published to trigger downstream processes (emails, indexing).
    *   **Amazon S3:** Stores raw resume files (PDF/Docx).
    *   **Amazon Textract / Bedrock:** Triggered via S3 upload events to extract text and generate summaries/rankings using LLMs.

4.  **Data Layer**
    *   **Amazon Aurora Serverless v2 (PostgreSQL):** The primary relational database for the Core Data Model (Jobs, Applications, Users).
    *   **Amazon OpenSearch Service:** For high-performance full-text search on candidate profiles and resumes.

### **Architecture Diagram**

```mermaid
graph TD
    subgraph Client_Layer
        Browser[Web Browser / Mobile]
    end

    subgraph Security
        Cognito[Amazon Cognito<br/>Auth & User Pool]
    end

    subgraph Entry_Point
        CF[CloudFront / Amplify]
        APIG[API Gateway<br/>REST API]
        AppSync[AWS AppSync<br/>Real-time GraphQL]
    end

    subgraph Compute_Logic
        LambdaAPI[Lambda Functions<br/>Core Logic]
        LambdaParser[Lambda Functions<br/>Resume Processor]
        LambdaNotif[Lambda Functions<br/>Notifications]
    end

    subgraph Data_Storage
        Aurora[(Aurora Serverless<br/>PostgreSQL)]
        S3[Amazon S3<br/>Resumes & Docs]
        OpenSearch[(OpenSearch<br/>Candidate Search)]
    end

    subgraph AI_Services
        Textract[Amazon Textract<br/>OCR]
        Bedrock[Amazon Bedrock<br/>LLM Ranking]
    end

    subgraph Event_Bus
        EB[Amazon EventBridge]
    end

    %% Flows
    Browser --> CF
    Browser -- Auth --> Cognito
    Browser -- REST Requests --> APIG
    Browser -- Real-time Scorecards --> AppSync

    APIG --> LambdaAPI
    AppSync --> LambdaAPI
    LambdaAPI --> Aurora

    %% Resume Upload Flow
    Browser -- Upload Resume --> S3
    S3 -- ObjectCreated Event --> LambdaParser
    LambdaParser --> Textract
    LambdaParser --> Bedrock
    LambdaParser -- Parsed Data --> Aurora
    LambdaParser -- Index Data --> OpenSearch

    %% Event Driven Flow
    LambdaAPI -- Status Change --> EB
    EB -- Trigger --> LambdaNotif
    LambdaNotif -- Send Email --> SES[Amazon SES]
```

## 9. C4 Container Diagram 🧩

This diagram details the **Candidate & Application Pipeline**, illustrating how the containers interact when a candidate submits an application and uploads a resume.

```mermaid
C4Container
    title Container Diagram - Candidate & Application Pipeline

    Person(candidate, "Candidate", "A user applying for a job.")
    
    System_Boundary(ats_system, "ATS System") {
        Container(web_app, "Web Application", "React, Amplify", "Provides the interface for candidates to apply.")
        Container(api_gateway, "API Gateway", "AWS API Gateway", "Entry point for application data.")
        Container(app_service, "Application Service", "AWS Lambda", "Handles application logic and data persistence.")
        Container(resume_bucket, "Resume Store", "Amazon S3", "Stores raw resume files.")
        Container(resume_processor, "Resume Processor", "AWS Lambda", "Event-driven function to process resumes.")
        ContainerDb(database, "Core Database", "Aurora PostgreSQL", "Stores candidate and application data.")
        Container(ai_service, "AI Service", "Textract & Bedrock", "Extracts text and ranks candidates.")
        ContainerQueue(event_bus, "Event Bus", "Amazon EventBridge", "Orchestrates async events.")
    }

    Rel(candidate, web_app, "Visits and applies", "HTTPS")
    Rel(web_app, api_gateway, "Submits form data", "JSON/HTTPS")
    Rel(web_app, resume_bucket, "Uploads resume", "HTTPS/Presigned URL")
    
    Rel(api_gateway, app_service, "Triggers", "HTTPS")
    Rel(app_service, database, "Writes application data", "SQL")
    Rel(app_service, event_bus, "Publishes 'Applied' event", "JSON")

    Rel(resume_bucket, resume_processor, "Triggers on Upload", "S3 Event")
    Rel(resume_processor, ai_service, "Requests parsing/ranking", "API")
    Rel(resume_processor, database, "Updates profile data", "SQL")
    Rel(resume_processor, event_bus, "Publishes 'Parsed' event", "JSON")
```


