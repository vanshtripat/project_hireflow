# 💼 HireFlow — Applicant Tracking System (ATS)

HireFlow is a professional-grade, multi-role **Applicant Tracking System (ATS)** designed to streamline the hiring workflow for Candidates, Recruiters, and Hiring Managers. Built as a high-fidelity, production-ready web application, HireFlow offers a seamless experience with zero-configuration setup, interactive dashboards, dynamic Kanban boards, and a simulation engine.

---

## 🌟 Key Features

### 🧑‍💼 1. Candidate Portal
- **Interactive Application Hub:** Candidates can browse open roles, track their application status in real-time, and view step-by-step progress.
- **Resume Upload & AI Parsing:** Simulated PDF parsing extracts education, experience, and contact details instantly using either a high-fidelity regex parsing engine or real Gemini API processing.
- **Interview Coordination:** Candidates can view upcoming schedules, submit RSVPs, and view feedback.

### 👩‍💻 2. Recruiter Command Center
- **Dynamic Kanban Pipeline:** Drag-and-drop or toggle candidates across hiring stages: *Applied, Resume Screening, Interview Scheduled, Offer Extended, Hired, or Rejected*.
- **Role & Job Management:** Create, edit, and archive job postings with detailed descriptions, requirements, and custom hiring stages.
- **Internal Collaboration:** Add collaborative screening notes, view parsed resume briefs, and schedule interviews with internal interviewers.

### 🤵 3. Hiring Manager Dashboard
- **Structured Review Flow:** Browse candidates forwarded for interview, rate skills, and submit standardized feedback.
- **Unified Analytics Suite:** Live visual metrics using Recharts representing application funnels, stage conversions, active pipelines, and interviewer workloads.
- **Decision Engine:** Seamlessly accept or reject candidate tracks, automatically generating live simulation audit logs.

### 📜 4. Global Simulation Logging
- **Real-Time Auditing:** A live terminal-style audit stream displays system-wide background actions (e.g., mail server triggers, database writes, user transitions).
- **Interactive Role Switcher:** Toggle instantly between candidate, recruiter, and hiring manager viewports to demo different user paths seamlessly.

---

## 🛠️ Tech Stack

- **Frontend:** React 19, TypeScript, Tailwind CSS, Recharts (Charts & Metrics), Lucide React (Icons)
- **Backend:** Node.js, Express.js, JSON File-Based Database (for portable zero-config execution), JWT Authentication
- **AI Integration:** Google Gemini API (via `@google/genai` with local high-fidelity regex fallback if key is omitted)
- **Tooling:** Vite, esbuild (for standalone production build bundles)

---

## 📂 Project Structure

```text
├── src/
│   ├── components/            # Interactive portal dashboards
│   │   ├── AnalyticsView.tsx       # Recharts dashboards & analytics metrics
│   │   ├── CandidateDashboard.tsx  # Applicant application tracking
│   │   ├── HiringManagerDashboard.ts # HM review panels & scoring
│   │   ├── RecruiterDashboard.tsx  # Kanban boards, job editors, confirm modals
│   │   └── LoginScreen.tsx         # Portals gateway & authentication
│   ├── server/
│   │   └── db.ts                   # Abstracted repository-pattern DB engine
│   ├── App.tsx                # Central routing, state hub, notifications, audit logging
│   ├── api.ts                 # Type-safe API client wrapper
│   ├── types.ts               # Shared ATS type definitions
│   └── main.tsx               # Client entrypoint
├── server.ts                  # Full-stack Express.js & Vite middleware server
├── SETUP.md                   # Step-by-step local setup & cloud scaling guide
├── .env.example               # Template for system-wide variables
├── package.json               # System dependencies and npm scripts
└── vite.config.ts             # Vite bundler options
```

---

## 🚀 Local Installation & Cloud Scaling

Please refer to **[SETUP.md](./SETUP.md)** for detailed, step-by-step setup instructions on:
1. **Running locally on Windows/OSX** using `npm install` and `npm run dev`.
2. **Connecting to MongoDB Atlas** in the cloud to transition from the default file database to a cloud-hosted relational/NoSQL environment.
3. **Setting up ImageKit** for actual PDF resume uploads and cloud document storage.
4. **Acquiring and configuring your Gemini API key** for advanced resume parsing.

---

### 🛡️ Production & Security Certified
HireFlow uses modern token-based **JWT session authentication**, secure client-side password hashing simulations, and clean API route error boundaries. No secrets or hardcoded credentials are committed to the codebase.
