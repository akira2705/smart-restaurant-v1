# Smart Restaurant — Queue & Table Management System (v1)

> Full-stack restaurant operations platform for managing walk-in queues, table reservations, and staff — built as a team project at Kumaraguru College of Technology.

---

## What it does

A web application that digitises restaurant floor management. Staff can track real-time table availability, manage a customer queue, handle reservations, and administer user accounts — all from a single dashboard.

### Pages

| Page | Role |
|---|---|
| Dashboard | Overview of tables, queue status, and stats |
| Tables | View and update table status (available / occupied / reserved) |
| Queue | Add customers to queue, call next, remove from queue |
| Reservations | Create, view, and manage upcoming reservations |
| Manager | Admin controls for user and settings management |

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Angular 20 + Angular Material |
| Backend | Express 5 + TypeScript |
| Database | SQLite (via better-sqlite3) |
| Auth | Session-based |
| Dev tooling | Nodemon, ts-node |

## Project Structure

```
smart-restaurant-v1/
├── BACKEND/
│   ├── src/
│   │   ├── controllers/   # queue, reservation, table, user
│   │   ├── routes/        # REST endpoints
│   │   ├── services/      # db.service.ts (SQLite connection)
│   │   └── app.ts         # Express app setup
│   ├── database.sql       # Schema
│   └── init-db.ts         # DB initialiser
└── FRONTEND/
    └── src/app/
        ├── pages/         # dashboard, queue, tables, reservation, manager
        ├── services/      # queue, table, user, reservation services
        └── shared/        # navbar, footer
```

## Getting Started

### Prerequisites

- Node.js >= 18
- npm

### Backend Setup

```bash
cd BACKEND

# Install dependencies
npm install

# Set up the database
# Option A — MySQL CLI:
mysql -u root -p < database.sql

# Option B — MySQL Workbench:
# Open database.sql and execute the script

# Create a .env file
cp .env.example .env
# Edit .env with your DB credentials:
#   DB_HOST=localhost
#   DB_USER=root
#   DB_PASS=your_password
#   DB_NAME=restaurant_db

# Start the dev server
npm run dev
```

Backend runs at `http://localhost:3000`

### Frontend Setup

```bash
cd FRONTEND

npm install
ng serve
```

Frontend runs at `http://localhost:4200`

> The frontend expects the backend at `http://localhost:3000`. Make sure the backend is running first.

## API Endpoints

| Method | Route | Description |
|---|---|---|
| GET/POST | `/api/users` | User management |
| GET/POST/PATCH | `/api/tables` | Table status |
| GET/POST/DELETE | `/api/queue` | Queue management |
| GET/POST/DELETE | `/reservations` | Reservations |

---

Made by Team 38 — Kumaraguru College of Technology
