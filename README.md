# Job Seeker – Job Portal Platform

A full-stack **Job Portal** that connects job seekers with employers. Users can search and apply for jobs, while employers can post openings and manage applicants.

This project is split across **three repositories**, representing an evolution from a single combined MERN app to a decoupled frontend + backend architecture:

| Repo | Purpose | Stack | Live Demo |
|---|---|---|---|
| [`Job_Seeker_MERN`](https://github.com/BIT-Project-Work/Job_Seeker_MERN) | Original all-in-one app (backend + server) | MongoDB, Express, React, Node.js | [job-portal-mern-jvuo.onrender.com](https://job-portal-mern-jvuo.onrender.com) |
| [`Job_Seeker_Frontend`](https://github.com/BIT-Project-Work/Job_Seeker_Frontend) | Standalone frontend | React + Vite | [job-portal-frontend-gamma-mauve.vercel.app](https://job-portal-frontend-gamma-mauve.vercel.app/) |
| [`Job_Seeker_NestJS`](https://github.com/BIT-Project-Work/Job_Seeker_NestJS) | Standalone backend (rewrite) | NestJS + TypeScript | [jobseeker-backend-nestjs.vercel.app](https://jobseeker-backend-nestjs.vercel.app/) |

> **Current direction:** the team is migrating away from the single MERN repo toward a decoupled **React frontend** talking to a **NestJS backend**.

---

## 1. Overview

The platform serves two types of users:

- **Job Seekers** – create a profile, browse/search job listings, and apply.
- **Employers** – post job openings, review applicants, and manage listings.

Core features (from the original MERN app, being carried into the new stack):
- User authentication (job seeker & employer roles)
- Job posting, editing, and deletion
- Job search & filtering
- Job applications with file uploads (resumes)
- Profile management

---

## 2. Repository Breakdown

### 🔹 `Job_Seeker_MERN` (Legacy / Reference)
The original combined app.
- **Structure:** `config/`, `controllers/`, `middleware/`, `models/`, `routes/`, `uploads/`, `utils/`, `server.js`
- **Stack:** Node.js + Express (backend), MongoDB (database)
- Serves as the reference implementation for business logic being ported to NestJS.

### 🔹 `Job_Seeker_Frontend`
A modern React frontend built with Vite.
- **Structure:** `src/`, `public/`, `Dockerfile`, `vite.config.js`
- **Stack:** React, Vite, ESLint
- Talks to the backend API via a configurable base URL (`baseUrl.js`)
- Deployable via Docker or Vercel (`vercel.json` included)

### 🔹 `Job_Seeker_NestJS`
The new backend, rebuilt with NestJS for better structure, scalability, and testing.
- **Structure:** `src/`, `test/`, `devops/`, `monitoring/`
- **Stack:** NestJS, TypeScript
- **Extras:** Includes production-grade tooling —
  - Dockerized (`Dockerfile`, `docker-compose.yml`)
  - CI workflows (`.github/workflows`)
  - Observability stack: Prometheus (`prometheus.yml`), Grafana dashboard (`dashboard.json`), Tempo tracing (`tempo/`)

---

## 3. Tech Stack Summary

| Layer | Technology |
|---|---|
| Frontend | React, Vite |
| Backend (legacy) | Node.js, Express |
| Backend (current) | NestJS, TypeScript |
| Database | MongoDB |
| DevOps / Monitoring | Docker, GitHub Actions, Prometheus, Grafana, Tempo |
| Deployment | Vercel, Render |

---

## 4. Getting Started

### Frontend (`Job_Seeker_Frontend`)
```bash
git clone https://github.com/BIT-Project-Work/Job_Seeker_Frontend.git
cd Job_Seeker_Frontend
npm install
npm run dev
```

### Backend – NestJS (`Job_Seeker_NestJS`)
```bash
git clone https://github.com/BIT-Project-Work/Job_Seeker_NestJS.git
cd Job_Seeker_NestJS
npm install

# development
npm run start:dev

# production
npm run start:prod
```
Or with Docker:
```bash
docker-compose up
```

### Backend – MERN (legacy, `Job_Seeker_MERN`)
```bash
git clone https://github.com/BIT-Project-Work/Job_Seeker_MERN.git
cd Job_Seeker_MERN
npm install
node server.js
```

---

## 5. Project Status

- ✅ MERN version — functional, deployed on Render
- ✅ Frontend rewrite — functional, deployed on Vercel
- 🚧 NestJS backend — actively being developed, includes monitoring/DevOps setup

---

## 6. Contributing

1. Fork the relevant repo
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Open a Pull Request

---

## 7. License

This project is for academic/learning purposes under BIT-Project-Work.
