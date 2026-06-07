# HRMS AI - Human Resource Management System

## Overview

HRMS AI is a full-stack Human Resource Management System developed using Go, PostgreSQL, and Google Gemini AI. The platform automates HR operations including employee management, attendance tracking, leave management, payroll processing, recruitment, AI-powered resume screening, and AI-based interview assessment.

The system provides secure JWT authentication, role-based authorization, candidate management workflows, and intelligent hiring assistance through Artificial Intelligence.

---

## Key Features

### Authentication & Security

* JWT-based Authentication
* Secure Login & Session Management
* Role-Based Access Control (RBAC)
* Protected API Routes
* Environment Variable Configuration

### Employee Management

* Employee CRUD Operations
* Department Management
* Employee Directory
* Employee Profile Management

### Attendance Management

* Daily Attendance Tracking
* Attendance Reports
* Employee Attendance History

### Leave Management

* Leave Application
* Leave Approval/Rejection
* Leave Status Tracking

### Payroll Management

* Payroll Generation
* Salary Management
* Payroll Updates and Tracking

### Recruitment Module

* Job Posting Management
* Public Career Portal
* Candidate Registration
* Resume Upload System

### AI Resume Screening

* Resume Parsing and Text Extraction
* Skill Matching Against Job Description
* Candidate Scoring
* Automated Recommendation Generation
* Shortlisting Support

### AI Interview Assessment

* AI-Generated Interview Questions
* Technical Skill Evaluation
* Communication Assessment
* Problem-Solving Evaluation
* Hiring Recommendations

### Performance Management

* Performance Reviews
* Employee Evaluation Tracking

### Dashboard & Analytics

* HR Dashboard
* Recruitment Dashboard
* Candidate Analytics
* Hiring Insights

### Notifications

* System Notifications
* Recruitment Updates
* Status Alerts

---

## Technology Stack

### Backend

* Go (Golang)
* Gin Framework
* JWT Authentication
* REST APIs

### Database

* PostgreSQL

### Artificial Intelligence

* Google Gemini API

### Frontend

* HTML5
* CSS3
* JavaScript

### File Processing

* PDF Resume Upload
* Resume Text Extraction

---

## Project Architecture

1. HR/Admin logs into the system.
2. HR creates job openings.
3. Candidates apply through the public application portal.
4. Resumes are uploaded and processed.
5. Candidate profiles are automatically created.
6. Resume text is extracted from uploaded PDFs.
7. AI performs resume screening against job requirements.
8. Candidate scores and recommendations are generated.
9. HR initiates AI-powered interviews.
10. AI generates interview questions.
11. Candidates submit responses.
12. AI evaluates responses and generates scores.
13. Interview reports and recommendations are stored.
14. HR makes the final hiring decision.

---

## Installation & Setup

### Clone Repository

```bash
git clone <repository-url>
cd hrms-ai
```

### Configure Environment Variables

Create a `.env` file using the following configuration:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=hrms
DB_USER=postgres
DB_PASSWORD=change-me
DB_SSLMODE=disable

PORT=8080

GEMINI_API_KEY=your-gemini-api-key
```

### Install Dependencies

```bash
go mod download
```

### Run Application

```bash
go run main.go
```

### Access Application

```text
http://localhost:8080/frontend/login.html
```

---

## Default Administrator Credentials

```text
Email    : admin@hrms.com
Password : admin123
```

---

## Core API Endpoints

### Authentication

```http
POST /api/auth/login
GET  /api/auth/me
```

### Employees

```http
GET    /api/employees
POST   /api/employees
PUT    /api/employees/{id}
DELETE /api/employees/{id}
```

### Jobs

```http
GET    /api/jobs
POST   /api/jobs
PUT    /api/jobs/{id}
DELETE /api/jobs/{id}
```

### Candidates

```http
POST /api/candidates/apply
GET  /api/candidates
POST /api/candidates/{id}/resume
POST /api/candidates/{id}/screen
GET  /api/candidates/{id}/analysis
```

### Interviews

```http
POST /api/interviews/start
GET  /api/interviews
GET  /api/interviews/{id}
PUT  /api/interviews/{id}/submit
```

---

## AI Resume Screening Output

```json
{
  "score": 84,
  "matching_skills": [],
  "missing_skills": [],
  "strengths": [],
  "weaknesses": [],
  "recommendation": "shortlist"
}
```

### Candidate Status Logic

```text
Score >= 80  → Shortlisted
Score >= 60  → Interviewing
Score < 60   → Rejected
```

---

## AI Interview Assessment Output

```json
{
  "technical_score": 80,
  "communication_score": 75,
  "problem_solving_score": 82,
  "overall_score": 79,
  "recommendation": "Maybe"
}
```

### Fallback Mechanism

If Gemini API quota or connectivity fails:

* Default interview questions are generated.
* Local assessment logic evaluates responses.
* Recruitment workflow continues without interruption.

---

## Security Measures

* Environment variables protected through `.env`
* JWT-secured APIs
* Role-Based Authorization
* Sensitive files excluded via `.gitignore`
* Upload directory protection
* Executable file restrictions

Ignored files:

```text
.env
uploads/
*.pdf
*.exe
```

---

## Future Enhancements

* Video Interview Analysis
* AI Candidate Ranking
* Email Notification Integration
* Employee Self-Service Portal
* Advanced HR Analytics
* Multi-Tenant Support
* Mobile Application

---

## Developed For

Academic Project / Final Year Project

HRMS AI demonstrates the integration of Human Resource Management processes with Artificial Intelligence to streamline recruitment, screening, interview assessment, and workforce management.
