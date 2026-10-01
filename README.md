# MIU Freelance Platform

A freelance platform for **Misr International University (MIU)** students. Students find real freelance work, and clients (staff, clubs, alumni) find trusted student talent.

> Status: 🚧 in development

---

## Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Database](#database)
- [Git Workflow](#git-workflow)
- [Roadmap](#roadmap)
- [Team](#team)

---

## About

Students have skills, but no trusted place to find real paid work. Clients often don't know which students to ask. This platform connects both sides in one place and builds trust through profiles and reviews.

**Roles**
- **Student:** creates a profile, browses jobs, applies, gets reviewed
- **Client:** posts jobs, reviews applicants, picks a student, leaves reviews
- **Admin:** manages users, jobs, and reviews

**Core flow**

```
Client posts job → Students apply → Client accepts one
→ Job in progress → Job completed → Both sides review
```

---

## Features

### MVP
- [ ] Register / login with MIU email, email verification, password reset
- [ ] Role-based access (student, client, admin)
- [ ] Student and client profiles
- [ ] Create, edit, and cancel jobs
- [ ] Browse jobs with search, filters, and pagination
- [ ] Apply to jobs with a message and proposed price
- [ ] Accept / reject applicants
- [ ] Job status tracking (open, in progress, completed, cancelled)
- [ ] Reviews and ratings
- [ ] Student and client dashboards
- [ ] Admin panel (manage users, jobs, reviews, basic stats)

### Planned
- [ ] Chat between client and student
- [ ] Notifications
- [ ] File uploads
- [ ] Arabic / English support

> Online payments are intentionally out of scope for the MVP.

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React |
| Backend | Node.js, Express |
| Database | PostgreSQL |
| ORM | Prisma |
| Version control | Git, GitHub |

---

## Project Structure

```
.
├── frontend/              # React app
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── hooks/
│       ├── context/
│       └── services/
├── backend/               # Express API
│   ├── prisma/
│   │   └── schema.prisma
│   └── src/
│       ├── routes/
│       ├── controllers/
│       ├── middleware/
│       └── utils/
├── MASTER_PLAN.md         # Full project plan and decisions
└── README.md
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (LTS version)
- [Git](https://git-scm.com/)
- [PostgreSQL](https://www.postgresql.org/) (or Docker)

### 1. Clone the repository

```bash
git clone <repo-url>
cd <project-folder>
```

### 2. Set up the backend

```bash
cd backend
npm install
cp .env.example .env        # then fill in your values
npx prisma migrate dev      # creates the database tables
npm run dev                 # starts the API
```

### 3. Set up the frontend

Open a new terminal:

```bash
cd frontend
npm install
cp .env.example .env        # then fill in your values
npm run dev                 # starts the React app
```

### 4. Open the app

- Frontend: http://localhost:5173
- Backend API: http://localhost:5000

*(Ports may differ depending on your setup.)*

---

## Environment Variables

**Never commit `.env` files.** Use `.env.example` as a template.

### `backend/.env`

```env
PORT=5000
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/freelance_db"
JWT_SECRET=change_this_to_a_long_random_string
CLIENT_URL=http://localhost:5173
```

### `frontend/.env`

```env
VITE_API_URL=http://localhost:5000
```

---

## Database

We use **Prisma** with **PostgreSQL**. The schema lives in `backend/prisma/schema.prisma`.

Useful commands (run from `backend/`):

```bash
npx prisma migrate dev      # apply changes and create a migration
npx prisma studio           # browse the database in your browser
npx prisma generate         # regenerate the Prisma client
```

After pulling changes that touch the schema, run `npx prisma migrate dev` again.

---

## Git Workflow

- **No direct pushes to `main`.**
- Create one branch per feature or fix:
  ```bash
  git checkout -b feature/job-posting
  ```
- Branch names: `feature/...`, `fix/...`, `docs/...`
- Write clear commit messages: `add job posting endpoint`, not `update`.
- Open a **pull request** and get at least one review before merging.
- Pull the latest `main` before starting new work.
- Keep tasks small, ideally 1 to 2 days each.

---

## Roadmap

| Phase | Goal | Status |
|-------|------|--------|
| 1 | Scope, design, repo setup, database schema | ⬜ |
| 2 | Auth and profiles | ⬜ |
| 3 | Jobs and applications (core flow end to end) | ⬜ |
| 4 | Reviews, dashboards, admin panel | ⬜ |
| 5 | Testing, polish, deployment | ⬜ |

See [`MASTER_PLAN.md`](./MASTER_PLAN.md) for the full plan.

---

## Team

| Name | Role | GitHub |
|------|------|--------|
| Mina Samaan | Team Lead | [@mina297](https://github.com/mina297) |
| Marina Ashraf | Member | [@Marina-Ashraf](https://github.com/Marina-Ashraf) |
| Marina Hanna | Member | [@marina2405238-cloud](https://github.com/marina2405238-cloud) |
| Carol Adel | Member | [@caroladel](https://github.com/caroladel) |
| Sama Mohamed | Member | [@SamaMohamed6](https://github.com/SamaMohamed6) |

---

## License

Developed as a university project at Misr International University (MIU). All rights reserved by the project team and the university.
