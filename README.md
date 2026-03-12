# 🏥 MediQueue AI — AI-Powered Hospital Queue Management System

> A smart digital platform that eliminates long hospital queues by enabling online appointment booking, AI-driven symptom analysis, real-time queue prediction, and live admin monitoring — built for government hospitals.

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4.x-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-AI-4285F4?style=for-the-badge&logo=google&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)


---

## 🚨 Problem Statement

Government hospitals in India face a critical challenge:
- Patients wait **3–6 hours** in queues just to register
- No visibility into doctor availability or waiting times
- Manual token systems cause chaos and long lines
- Emergency patients get stuck behind routine checkups
- Doctors have no data on upcoming patient load

**MediQueue AI solves all of this** with a zero-friction digital system.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 📅 **Smart Appointment Booking** | Book with department, doctor & time slot selection — get instant token confirmation |
| 🧠 **AI Symptom Analyzer** | Describe symptoms → AI recommends the right department and priority level |
| ⏱️ **Real-Time Queue Prediction** | Live estimated waiting time based on current queue data |
| 🤖 **AI Helpdesk Chatbot** | Ask anything about doctors, timings, departments, or bookings |
| 📊 **Admin Dashboard** | Live charts for patient flow, department load, appointment stats |
| 👨‍⚕️ **Doctor Management** | Add/edit/remove doctors, set schedules, toggle availability |
| 📺 **Live Queue Display Board** | Dark-theme public display showing currently serving and waiting patients |
| 🔔 **Browser Notifications** | Instant booking confirmation via browser push notifications |

---

## 🚀 Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/your-username/mediqueue-ai.git
cd mediqueue-ai

# 2. Install dependencies
npm install

# 3. Start the server
npm start

# 4. Open in browser
# http://localhost:3000
```

> ✅ Works out of the box — no database or API keys required. Uses in-memory storage and built-in AI fallback for demo.

---

## 🧱 Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | HTML5, CSS3 (Custom Glassmorphism UI), Vanilla JavaScript, Chart.js |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB Atlas (with automatic in-memory fallback) |
| **AI Engine** | Google Gemini API / OpenAI API / Built-in rule-based fallback |
| **Notifications** | Browser Notification API |
| **Auth** | Session token-based admin authentication |

---

## 📁 Project Structure

```
mediqueue-ai/
├── backend/
│   ├── server.js                  # Main Express server + seed data
│   ├── database/
│   │   └── database-config.js     # MongoDB connection with fallback
│   ├── models/
│   │   ├── Appointment.js         # Appointment Mongoose schema
│   │   └── Doctor.js              # Doctor Mongoose schema
│   └── routes/
│       ├── appointments.js        # Appointment CRUD + queue logic
│       ├── doctors.js             # Doctor CRUD
│       └── ai.js                  # AI symptom analysis + chatbot
├── frontend/
│   ├── index.html                 # Home / Landing page
│   ├── booking.html               # Appointment booking form
│   ├── symptom-analyzer.html      # AI symptom analyzer
│   ├── chatbot.html               # AI chatbot interface
│   ├── admin-login.html           # Admin authentication
│   ├── admin-dashboard.html       # Analytics dashboard
│   ├── doctor-management.html     # Doctor CRUD panel
│   ├── queue-display.html         # Public queue display board
│   ├── css/
│   │   └── styles.css             # All styles, animations, responsive
│   └── js/
│       ├── main.js                # Shared utilities + API_BASE config
│       ├── booking.js             # Booking page logic
│       ├── symptom-analyzer.js    # Symptom analyzer logic
│       ├── chatbot.js             # Chatbot logic
│       ├── admin-dashboard.js     # Dashboard charts & stats
│       ├── doctor-management.js   # Doctor management logic
│       └── queue-display.js       # Live queue polling
├── .env.example                   # Environment variable template
├── package.json
└── README.md
```

---

## 🔌 API Reference

### Appointments

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/appointments` | Book new appointment |
| `GET` | `/api/appointments` | List appointments (filter by date, dept, status) |
| `GET` | `/api/appointments/stats` | Dashboard statistics |
| `GET` | `/api/appointments/queue` | Live queue display data |
| `PATCH` | `/api/appointments/:id/status` | Update appointment status |
| `POST` | `/api/appointments/predict-waiting-time` | Get wait time prediction |

### Doctors

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/doctors` | Add new doctor |
| `GET` | `/api/doctors` | Get all doctors (filter by dept, availability) |
| `GET` | `/api/doctors/:id` | Get doctor by ID |
| `PUT` | `/api/doctors/:id` | Update doctor details |
| `DELETE` | `/api/doctors/:id` | Remove doctor |

### AI

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/ai/analyze-symptoms` | Analyze symptoms → suggest department + priority |
| `POST` | `/api/ai/chat` | Chatbot conversation |

### Admin

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/admin/login` | Admin login → returns session token |
| `POST` | `/api/admin/verify` | Verify session token |
| `POST` | `/api/admin/logout` | Invalidate session token |

---

## 📱 Pages Overview

| Page | URL | Access |
|------|-----|--------|
| 🏠 Home | `/` | Public |
| 📅 Book Appointment | `/booking.html` | Public |
| 🧠 Symptom Analyzer | `/symptom-analyzer.html` | Public |
| 🤖 AI Chatbot | `/chatbot.html` | Public |
| 📺 Queue Display | `/queue-display.html` | Public |
| 🔐 Admin Login | `/admin-login.html` | Admin |
| 📊 Admin Dashboard | `/admin-dashboard.html` | Admin |
| 👨‍⚕️ Doctor Management | `/doctor-management.html` | Admin |

> **Default Admin Credentials:** `admin` / `admin123`

---

## 🎯 Demo Flow

```
Patient                          Admin
  │                                │
  ├─ Opens home page               ├─ Logs in to dashboard
  ├─ Enters symptoms               ├─ Monitors live queue charts
  ├─ AI suggests department        ├─ Updates appointment statuses
  ├─ Selects doctor + time slot    ├─ Manages doctor availability
  ├─ Gets token + wait time        └─ Views department-wise analytics
  └─ Sees queue on display board
```

---

## 🤖 AI Setup (Optional)

The project works without any API keys using the built-in rule-based AI. For smarter responses:

### Google Gemini (Recommended — Free tier)
```env
AI_PROVIDER=gemini
GEMINI_API_KEY=your_key_here
```
Get key: https://aistudio.google.com/apikey

### OpenAI
```env
AI_PROVIDER=openai
OPENAI_API_KEY=your_key_here
```

---

## 🗃️ MongoDB Setup (Optional)

Default mode uses in-memory storage (data resets on server restart).

For persistent storage with MongoDB Atlas:
```env
MONGODB_URI=mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/mediqueue
```
Create free cluster: https://www.mongodb.com/atlas

---

## 🎨 UI Highlights

- Glassmorphism card components with blur/shadow effects
- Blue → Teal → Green hospital-theme gradient palette
- Smooth CSS transitions and entrance animations
- Fully responsive — Mobile, Tablet, Desktop
- Chart.js visualizations: Bar, Line, Pie, Doughnut
- Toast notification system with slide-in animation
- Animated counters and wait-time progress bars
- Dark-themed public queue display board

---

## 🏆 Built For

**Smart India Hackathon (SIH)** — Problem Statement: Digital transformation of OPD queue management in government hospitals.

---

## 📄 License

MIT License — free to use, modify, and distribute.

