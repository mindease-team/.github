<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100=0f3460&height=200&section=header&text=MindEase&fontSize=72&fontColor=e94560&animation=fadeIn&fontAlignY=38&desc=AI-Powered%20Mental%20Wellness%20Companion&descAlignY=58&descColor=a8b2d8" width="100%"/>

<br/>

![Vue.js](https://img.shields.io/badge/Vue.js_3-4FC08D?style=for-the-badge&logo=vuedotjs&logoColor=white)
![Go](https://img.shields.io/badge/Go_Fiber_v3-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle_DB-F80000?style=for-the-badge&logo=oracle&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Gemini_Flash_AI-4285F4?style=for-the-badge&logo=google&logoColor=white)
![DigitalOcean](https://img.shields.io/badge/DigitalOcean-0080FF?style=for-the-badge&logo=digitalocean&logoColor=white)

<br/>

> *Your personal AI companion for emotional wellbeing — track moods, journal thoughts, chat with AI, and get weekly mental health insights.*

<br/>

</div>

---

## 🧠 What is MindEase?

MindEase is a full-stack AI-powered mental wellness web application built as a **Software Engineering Thesis Project** at BELTEI International University. It helps the general public understand their emotions and improve their mental wellbeing through intelligent, personalized tools.

Whether you're feeling overwhelmed, anxious, or just want to reflect on your day — **MindEase is always there.**

---

## ✨ Features

<table>
  <tr>
    <td width="50%">
      <h3>😊 Mood Check-in</h3>
      <p>Log your daily mood with an intensity level and optional note. Get an instant empathetic AI response tailored to how you feel.</p>
    </td>
    <td width="50%">
      <h3>📓 Guided Journaling</h3>
      <p>Receive 3 personalized AI-generated journal prompts based on your current mood. AI reflects on your responses when you're done.</p>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>💬 AI Chat Companion</h3>
      <p>Talk to a supportive AI agent anytime. Vent, ask for coping strategies, or just chat. Includes built-in crisis detection for user safety.</p>
    </td>
    <td width="50%">
      <h3>📊 Mood Dashboard</h3>
      <p>Visualize your emotional patterns over days and weeks with interactive charts. Track your daily wellness streaks.</p>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>📋 Weekly AI Report</h3>
      <p>Every 7 days, AI auto-generates a full mental health report — mood trends, emotional triggers, and improvement suggestions.</p>
    </td>
    <td width="50%">
      <h3>🛡️ Admin Panel</h3>
      <p>Full admin dashboard for user management, crisis alert monitoring, platform analytics, and system health tracking.</p>
    </td>
  </tr>
</table>

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────┐
│              Vue.js 3 Frontend                    │
│        User App  ·  Admin Panel                   │
└─────────────────────┬────────────────────────────┘
                      │  HTTP · Axios
                      ▼
┌──────────────────────────────────────────────────┐
│             Go Fiber v3 Backend                   │
│                                                   │
│   /api/*          →   User API                    │
│   /admin-api/*    →   Admin API                   │
│                                                   │
│   Handler → Service → Repository → Oracle DB      │
│                   │                               │
│             AI Agent Layer                        │
└─────────────────────┬────────────────────────────┘
                      │
         ┌────────────┴────────────┐
         ▼                         ▼
   ┌───────────┐         ┌──────────────────┐
   │ Oracle DB │         │ Gemini Flash API  │
   └───────────┘         └──────────────────┘
```

---

## 📁 Repositories

| Repository | Description | Owner |
|-----------|-------------|-------|
| [🎨 mindease-frontend](https://github.com/mindease-team/mindease-frontend) | Vue.js 3 — user app and admin panel | Hok Do |
| [⚙️ mindease-backend](https://github.com/mindease-team/mindease-backend) | Go Fiber v3 — API, AI agent, business logic | Cheang Odom |
| [🗄️ mindease-database](https://github.com/mindease-team/mindease-database) | Oracle DB schema, indexes, migrations | LyhengLT |

---

## 🗄️ Database

**9 tables** powering the full platform:

```
admins           →  admin accounts
users            →  registered user accounts
mood_entries     →  daily mood logs + AI responses
journal_entries  →  AI prompts, responses, reflections
chat_sessions    →  conversation session groups
chat_messages    →  individual chat messages
reports          →  weekly AI mental health reports
crisis_flags     →  AI-flagged distress alerts
admin_logs       →  full admin audit trail
```

---

## 📡 API

<details>
<summary><b>User API — /api</b></summary>

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/auth/register` | Register new user |
| `POST` | `/api/auth/login` | Login and get JWT |
| `POST` | `/api/mood` | Log a mood entry |
| `GET` | `/api/mood` | Get mood history |
| `GET` | `/api/journal/prompts` | Get AI journal prompts |
| `POST` | `/api/journal` | Save journal entry |
| `POST` | `/api/chat` | Send chat message |
| `GET` | `/api/chat/history` | Get chat history |
| `GET` | `/api/report` | Get weekly report |
| `POST` | `/api/report/generate` | Generate weekly report |

</details>

<details>
<summary><b>Admin API — /admin-api</b></summary>

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/admin-api/auth/login` | Admin login |
| `GET` | `/admin-api/users` | Get all users |
| `PUT` | `/admin-api/users/:id/deactivate` | Deactivate user |
| `PUT` | `/admin-api/users/:id/ban` | Ban user |
| `GET` | `/admin-api/analytics` | Platform analytics |
| `GET` | `/admin-api/crisis-alerts` | Get crisis flags |
| `PUT` | `/admin-api/crisis-alerts/:id/review` | Mark as reviewed |
| `GET` | `/admin-api/system` | System health stats |

</details>

---

## 🚀 Deployment

```
Namecheap Domain
       │
       ▼
DigitalOcean Droplet
       │
       ├── Nginx → serves Vue.js /dist + proxies /api to Go Fiber
       └── Go Fiber (PM2) → connects to Oracle Cloud DB
```

| Service | Cost |
|---------|------|
| DigitalOcean Droplet | ~$6/month |
| Oracle Cloud DB | Free |
| Let's Encrypt SSL | Free |
| Gemini Flash API | ~$5–15 total |
| Namecheap Domain | ~$10/year |

---

## 📌 Project Status

| Milestone | Status |
|-----------|--------|
| Project planning & architecture | ✅ Complete |
| Database schema design | ✅ Complete |
| Backend scaffolding | 🔄 In Progress |
| Frontend scaffolding | 🔄 In Progress |
| AI agent integration | ⏳ Upcoming |
| Admin panel | ⏳ Upcoming |
| Deployment | ⏳ Upcoming |

---

## 👥 Team

<table>
  <tr>
    <td align="center" width="33%">
      <b>Lyheng Lay</b><br/>
      <i>Team Lead · DB · Deployment · Admin</i><br/>
      <sub>Oracle schema · DigitalOcean · Nginx · PM2 · SSL · Admin pages</sub>
    </td>
    <td align="center" width="33%">
      <b>Hok Do</b><br/>
      <i>Frontend Developer</i><br/>
      <sub>Vue.js · Pinia · Vue Router · Chart.js · UI/UX</sub>
    </td>
    <td align="center" width="33%">
      <b>Cheang Odom</b><br/>
      <i>Backend Developer</i><br/>
      <sub>Go Fiber · AI Agent · Handler/Service/Repository · Oracle</sub>
    </td>
  </tr>
</table>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100=0f3460&height=100&section=footer" width="100%"/>

<sub>🎓 Software Engineering Thesis Project · BELTEI International University · Built with Vue.js · Go Fiber · Oracle DB · Google Gemini AI</sub>

</div>
