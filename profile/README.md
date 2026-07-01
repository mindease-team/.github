<div align="center">

# 🧠 MindEase — AI Mental Wellness Companion

**A full-stack AI-powered mental wellness platform that helps you track your mood, journal your thoughts, and talk to an empathetic AI companion — 24/7, for free.**

[![Vue](https://img.shields.io/badge/Vue-3.x-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)
[![Go](https://img.shields.io/badge/Go-Fiber%20v3-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://gofiber.io/)
[![Oracle](https://img.shields.io/badge/Oracle-ATP%2026ai-F80000?style=for-the-badge&logo=oracle&logoColor=white)](https://www.oracle.com/cloud/free/)
[![Gemini](https://img.shields.io/badge/Gemini-2.5%20Pro-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white)](https://ai.google.dev/)
[![Netlify](https://img.shields.io/badge/Netlify-Frontend-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)](https://www.netlify.com/)
[![Railway](https://img.shields.io/badge/Railway-Backend-0B0D0E?style=for-the-badge&logo=railway&logoColor=white)](https://railway.app/)

[Live App](https://mindeasebiu.netlify.app) · [Admin Panel](https://mindeasebiu.netlify.app/admin/login) · [API](https://mindease-backend-production-88ea.up.railway.app)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Live Demo](#-live-demo)
- [Features](#-features)
  - [User Features](#-user-features-14)
  - [Admin Features](#-admin-features-5)
- [AI Capabilities](#-ai-capabilities)
- [Tech Stack](#-tech-stack)
- [Architecture & Project Structure](#-architecture--project-structure)
- [API Endpoints](#-api-endpoints)
- [Database Schema](#-database-schema)
- [Security](#-security)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Screenshots](#-screenshots)
- [Team](#-team)

---

## 🌱 Overview

**MindEase** is a full-stack AI-powered mental wellness web application built as a final-year university project at **BELTEI International University**. It combines mood tracking, AI journaling, an empathetic chat companion, and a library of self-care tools into a single accessible platform, backed by real-time crisis detection and an admin analytics dashboard.

---

## 🚀 Live Demo

| Environment | URL |
|---|---|
| 🌐 App | [mindeasebiu.netlify.app](https://mindeasebiu.netlify.app) |
| 🛡️ Admin Panel | [mindeasebiu.netlify.app/admin/login](https://mindeasebiu.netlify.app/admin/login) |
| 🔌 API | [mindease-backend-production-88ea.up.railway.app](https://mindease-backend-production-88ea.up.railway.app) |

**Test Accounts**

| Role | Email | Password |
|---|---|---|
| 👤 User | `test@mindease.com` | `test123` |
| 🛡️ Admin | `admin@mindease.com` | `admin123` |

---

## ✨ Features

### 👤 User Features (14)

| # | Feature | Description |
|---|---|---|
| 1 | 💬 **AI Chat** | Empathetic conversational AI with session memory and context awareness |
| 2 | 😊 **Mood Check-in** | Emoji selector, intensity slider (1–5), notes, AI-powered supportive responses |
| 3 | 📓 **AI Journal** | Personalized prompts based on mood history, AI reflections on entries |
| 4 | 📊 **Weekly Reports** | AI-generated wellness summaries with mood trends, triggers, and suggestions |
| 5 | 🗓️ **Mood Calendar** | Monthly heatmap visualization of mood history |
| 6 | 🌬️ **Breathing Exercises** | Box breathing, 4-7-8 technique, guided relaxation with animated visuals |
| 7 | 😴 **Sleep Tracker** | Log and track sleep quality over time |
| 8 | 🧘 **Self-Care Activities** | Body scan, gratitude journaling, nature sounds, progressive muscle relaxation |
| 9 | 🎮 **Stress Relief Games** | Memory Match, Bubble Pop, Color Tap, Zen Patterns |
| 10 | 🏆 **Achievements** | Badges and milestones for consistent wellness tracking |
| 11 | 💡 **Daily Wellness Tips** | Curated tips and quotes that rotate daily |
| 12 | 🆘 **SOS Crisis Support** | 5-4-3-2-1 grounding technique, crisis hotlines, safety planning |
| 13 | ⚙️ **Settings** | Profile management, password change, dark mode toggle |
| 14 | 🌙 **Dark Mode** | Full dark theme support across the entire app |

### 🛡️ Admin Features (5)

| # | Feature | Description |
|---|---|---|
| 1 | 📈 **Analytics Dashboard** | Real-time charts — user growth, mood distribution, engagement, weekly activity |
| 2 | 👥 **User Management** | View, activate, deactivate, ban users with search and filter |
| 3 | 🚨 **Crisis Alerts** | AI-flagged crisis messages sorted by severity (low / medium / high) |
| 4 | 🩺 **System Health** | Database connection stats, API uptime, open connections monitoring |
| 5 | 🔐 **Admin Settings** | Profile and security management |

---

## 🤖 AI Capabilities

Powered by **Google Gemini 2.5 Pro**:

- 💬 Empathetic conversational AI with session-based memory
- 😊 Mood analysis with personalized supportive responses
- 📓 Personalized journal prompt generation based on mood history
- 💭 AI reflections on journal entries
- 🚨 Automatic crisis detection — analyzes messages for self-harm indicators and flags by severity
- 📊 Weekly wellness report generation with mood trends and actionable suggestions

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | Vue 3 + Vite (SPA), Vue Router, Pinia |
| **Backend** | Go + Fiber v3 (REST API, 37 endpoints) |
| **Database** | Oracle Cloud ATP 26ai (Always Free Tier, `ap-sydney-1`) |
| **DB Driver** | `go-ora` (pure Go Oracle driver, mTLS wallet auth) |
| **AI** | Google Gemini 2.5 Pro (REST API) |
| **Auth** | JWT (separate user/admin secrets) + Google OAuth 2.0 |
| **Hosting** | Netlify (frontend) · Railway + Docker (backend) · Oracle Cloud (DB) |

---

## 🏗️ Architecture & Project Structure

**GitHub Organization:** [github.com/mindease-team](https://github.com/mindease-team) — three repositories, documented together in this README.

<details>
<summary><strong>📁 mindease-frontend/</strong> — Vue 3 SPA</summary>

```
mindease-frontend/
├── src/
│   ├── views/
│   │   ├── LandingPage.vue
│   │   ├── user/        # 14 pages: Dashboard, MoodCheckIn, Journal, Chat,
│   │   │                # Report, Settings, Breathing, SOS, SleepTracker,
│   │   │                # SelfCare, Games, Achievements, WellnessTips, Login, Register
│   │   └── admin/       # 5 pages: Login, Dashboard, Users, CrisisAlerts, System, Settings
│   ├── components/      # NavBar, UserLayout, MoodChart, MoodCalendar,
│   │                     # MoodSelector, ChatBubble, ChatWindow, ReportCard
│   ├── stores/          # authStore, adminStore (Pinia)
│   ├── services/        # API service layer with mock/real toggle per feature
│   └── router/          # Vue Router with auth guards
├── public/_redirects    # Netlify SPA routing
└── .env / .env.production
```
</details>

<details>
<summary><strong>📁 mindease-backend/</strong> — Go Fiber v3 REST API</summary>

```
mindease-backend/
├── main.go                    # Entry point, server setup
├── config/                    # Environment config loader
├── handlers/
│   ├── user/                  # auth.go, mood.go, journal.go, chat.go, report.go, settings.go
│   └── admin/                 # auth.go, user.go, crisis.go, analytics.go, system.go
├── services/
│   ├── user/                  # auth.go, mood.go, journal.go, chat.go, report.go, settings.go
│   ├── admin/                 # auth.go, user.go, crisis.go
│   └── geminiService.go       # Google Gemini 2.5 Pro integration
├── models/                    # user.go, mood.go, journal.go, chat.go, report.go, crisis.go, admin.go
├── repositories/               # Database access layer per model
├── routes/
│   ├── user/routes.go
│   └── admin/routes.go
├── middleware/                 # JWT auth middleware
├── wallet/                     # Oracle mTLS wallet files
├── Dockerfile                  # Multi-stage: golang:1.26-alpine → alpine:3.19
└── .env.example
```
</details>

<details>
<summary><strong>📁 mindease-database/</strong> — Oracle Cloud ATP 26ai</summary>

```
mindease-database/
├── schema.sql          # 9 tables
├── views.sql           # 8 views
├── triggers.sql        # 9 triggers
├── procedures.sql      # 8 stored procedures
├── indexes.sql         # Performance indexes
├── seed.sql            # Test data
├── drop.sql            # Cleanup script
└── docker-compose.yml  # Local Oracle 21c XE for development
```
</details>

---

## 🔌 API Endpoints

**37 total endpoints**

<details>
<summary><strong>👤 User Endpoints</strong></summary>

| Category | Method | Endpoint |
|---|---|---|
| Auth | `POST` | `/api/auth/register` |
| Auth | `POST` | `/api/auth/login` |
| Auth | `POST` | `/api/auth/google` |
| Mood | `POST` | `/api/mood` |
| Mood | `GET` | `/api/mood/history` |
| Mood | `GET` | `/api/mood/calendar` |
| Journal | `POST` | `/api/journal/prompts` |
| Journal | `POST` | `/api/journal` |
| Journal | `GET` | `/api/journal/history` |
| Chat | `POST` | `/api/chat` |
| Chat | `GET` | `/api/chat/history` |
| Report | `GET` | `/api/report/latest` |
| Report | `POST` | `/api/report/generate` |
| Settings | `GET` | `/api/settings` |
| Settings | `PUT` | `/api/settings` |
| Settings | `PUT` | `/api/settings/password` |

</details>

<details>
<summary><strong>🛡️ Admin Endpoints</strong></summary>

| Category | Method | Endpoint |
|---|---|---|
| Auth | `POST` | `/api/admin/auth/login` |
| Users | `GET` | `/api/admin/users` |
| Users | `PUT` | `/api/admin/users/:id/status` |
| Crisis | `GET` | `/api/admin/crisis` |
| Crisis | `PUT` | `/api/admin/crisis/:id` |
| Analytics | `GET` | `/api/admin/analytics/overview` |
| Analytics | `GET` | `/api/admin/analytics/charts` |
| System | `GET` | `/api/admin/system/health` |

</details>

---

## 🗄️ Database Schema

Hosted on **Oracle Cloud ATP 26ai** (Always Free Tier):

| Component | Count | Description |
|---|---|---|
| 📋 Tables | 9 | `users`, `moods`, `journal_entries`, `chat_sessions`, `chat_messages`, `reports`, `crisis_alerts`, `admin_users`, `admin_logs` |
| 👁️ Views | 8 | Analytics and reporting |
| ⚡ Triggers | 9 | Auto-timestamps, defaults, cascading |
| 🔧 Stored Procedures | 8 | Complex operations |
| 🔍 Indexes | — | Performance-tuned |

---

## 🔒 Security

- ✅ JWT authentication with **separate user and admin secrets**
- ✅ Google OAuth 2.0 one-click social login
- ✅ Oracle **mTLS wallet-based** mutual TLS encryption for database access
- ✅ CORS origin-restricted API access
- ✅ bcrypt password hashing
- ✅ Vue Router guards for protected routes

---

## ⚡ Getting Started

### 1️⃣ Database

**Option A — Docker (local dev)**
```bash
cd mindease-database
docker-compose up -d
# Then run: schema.sql → views.sql → triggers.sql → procedures.sql → seed.sql
```

**Option B — Oracle Cloud ATP (production)**
```bash
# 1. Create an Always Free ATP instance on Oracle Cloud
# 2. Download the wallet
# 3. Place it in mindease-backend/wallet/
```

### 2️⃣ Backend

```bash
cd mindease-backend
cp .env.example .env
# Fill in: DB_DSN, WALLET_DIR, JWT_SECRET, JWT_ADMIN_SECRET, GEMINI_API_KEY
go run main.go
# API runs on http://localhost:8080
```

### 3️⃣ Frontend

```bash
cd mindease-frontend
npm install
npm run dev
# App runs on http://localhost:5173
# For mock mode (no backend required): set VITE_MOCK_API=true in .env
```

---

## 🔧 Environment Variables

**Frontend** (`mindease-frontend/.env`)
```env
VITE_APP_NAME=MindEase
VITE_API_BASE_URL=http://localhost:8080
VITE_MOCK_API=false
VITE_GOOGLE_CLIENT_ID=your-google-oauth-client-id
```

**Backend** (`mindease-backend/.env`)
```env
PORT=8080
DB_DSN=oracle://ADMIN:password@host:1522/service_name
WALLET_DIR=./wallet
JWT_SECRET=your-jwt-secret
JWT_ADMIN_SECRET=your-admin-jwt-secret
GEMINI_API_KEY=your-gemini-api-key
CORS_ORIGINS=http://localhost:5173,https://mindeasebiu.netlify.app
```

---

## 📸 Screenshots

<div align="center">

| Dashboard | AI Chat | Mood Calendar |
|---|---|---|
| _screenshot placeholder_ | _screenshot placeholder_ | _screenshot placeholder_ |

| Admin Analytics | Journal | SOS Crisis Support |
|---|---|---|
| _screenshot placeholder_ | _screenshot placeholder_ | _screenshot placeholder_ |

</div>

---

## 👥 Team

| Name | Role |
|---|---|
| **Lay Ly Heng** | Team Lead, Database |
| **Hok Do** | Frontend |
| **Cheang Odom** | Backend |

**University:** BELTEI International University
**Professor:** Chen Sovann
**Course:** AI Final Project — July 2026

---

<div align="center">

Made with ❤️ by **MindEase Team**

</div>
