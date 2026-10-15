# 🎓 StudyMate - Full Stack Student Assignment Tracker

A complete, modern **Full Stack Web Application** organized cleanly with **Frontend** and **Backend**:
- **Frontend**: React 18 (Vite), Plain CSS3, Responsive UI Dashboard
- **Backend**: Node.js & Express REST API (`/api/tasks`, `/api/health`, etc.)
- **Database**: Server-side JSON Store (`backend/server/tasks.json`) + Client-side `localStorage` caching
- **GitHub Repository**: [https://github.com/Manishsai878/StudyMate](https://github.com/Manishsai878/StudyMate)

---

## 📁 Repository Structure

```text
StudyMate/
├── frontend/                     # React + Vite Client Application
│   ├── public/
│   │   └── tasks.json            # Initial starter tasks
│   ├── src/
│   │   ├── App.jsx               # Main React Dashboard Component
│   │   ├── App.css               # Component styling & layout
│   │   ├── index.css             # Design tokens & typography
│   │   └── main.jsx              # React DOM mounting
│   ├── index.html                # Entry HTML with Google Fonts
│   ├── vite.config.js            # Vite configuration with API proxy
│   ├── package.json              # Frontend dependencies
│   └── .gitignore                # Frontend gitignore
│
├── backend/                      # Node.js + Express REST API Server
│   ├── server/
│   │   └── tasks.json            # Server-side JSON database
│   ├── server.js                 # Express server & REST API endpoints
│   ├── package.json              # Backend dependencies
│   └── .gitignore                # Backend gitignore
│
├── package.json                  # Root runner script configuration
├── .gitignore                    # Root gitignore (ignores node_modules & dist)
└── README.md                     # Comprehensive project documentation
```

---

## 🛠️ Full Stack Architecture

```text
┌────────────────────────────────────────────────────────┐
│                   CLIENT (BROWSER)                     │
│  React Dashboard UI (frontend/src/App.jsx)             │
│  Runs on: http://localhost:5173                        │
└───────────────────────────▲────────────────────────────┘
                            │  HTTP Requests (fetch /api/*)
                            │  (GET / POST / PUT / DELETE)
┌───────────────────────────▼────────────────────────────┐
│              EXPRESS SERVER (backend/server.js)        │
│  • Runs on: http://localhost:5000                      │
│  • Serves REST API endpoints (/api/tasks)              │
│  • Data persistence in backend/server/tasks.json       │
└────────────────────────────────────────────────────────┘
```

---

## 🔌 Backend REST API Endpoints

| Method | Endpoint | Description | Request Body |
|---|---|---|---|
| `GET` | `/api/health` | Check backend server status | None |
| `GET` | `/api/tasks` | Get all assignments | None |
| `POST` | `/api/tasks` | Add a new assignment | `{ title, subject, deadline, priority }` |
| `PUT` | `/api/tasks/:id` | Toggle / update task status | `{ completed: boolean }` |
| `DELETE` | `/api/tasks/:id` | Delete an assignment | None |
| `POST` | `/api/tasks/reset` | Restore initial demo assignments | None |

---

## 🚀 Getting Started & How to Run

### Option 1: Run Both from the Project Root

1. **Install Dependencies**:
   ```bash
   npm install --prefix frontend
   npm install --prefix backend
   ```

2. **Start Backend Server**:
   ```bash
   npm run server
   ```
   *Runs on `http://localhost:5000`*

3. **Start Frontend (in a second terminal)**:
   ```bash
   npm run dev
   ```
   *Runs on `http://localhost:5173` with instant Vite Hot Module Replacement (HMR)*

---

### Option 2: Run Frontend and Backend Independently

#### To Run Frontend:
```bash
cd frontend
npm install
npm run dev
```

#### To Run Backend:
```bash
cd backend
npm install
npm start
```

---

## ✨ Application Features

1. **📊 Real-Time Dashboard Summary Cards**:
   - Total assignments counter.
   - Completed tasks counter.
   - Pending tasks counter.
   - Updates immediately when any task is added, marked complete, or deleted.

2. **📈 Dynamic Progress Bar**:
   - CSS progress track displaying real-time completion percentage (0% to 100%).
   - Motivational status caption based on completion level.

3. **➕ Add Assignment Form**:
   - Assignment Title with validation.
   - Subject selection (React JS, DBMS, Python, ML, HTML & Web Tech, CSS, etc.).
   - Due Date picker.
   - Priority selection (High 🔴, Medium 🟡, Low 🟢).

4. **📋 Interactive Task Cards**:
   - Subject badge, priority indicator, and formatted due date.
   - Overdue warning flag (`⚠️ Overdue`) for expired deadlines.
   - Strikethrough visual styling when completed.
   - Quick one-click checkbox and Undo / Complete buttons.
   - Delete confirmation modal.

5. **🔍 Real-Time Search & Status Filters**:
   - Filter tabs: **All**, **Pending**, and **Completed**.
   - Real-time search query matching both Title and Subject.

6. **💾 Dual Persistence (Backend API + LocalStorage Fallback)**:
   - Server persistence via `backend/server/tasks.json`.
   - Browser `localStorage` cache for offline resilience.
   - "Reset Demo Data" button to restore initial sample tasks anytime.

---

## 🎓 Viva & Exam Questions (Quick Review)

- **Q1: Why is the repository separated into frontend and backend?**
  - **Answer**: Separating frontend and backend creates modularity, follows standard industry architecture, allows independent scaling and deployment, and separates client UI logic from server data logic.
- **Q2: How does the frontend communicate with the backend?**
  - **Answer**: The frontend uses standard HTTP `fetch()` requests to call REST endpoints (`GET`, `POST`, `PUT`, `DELETE` on `/api/tasks`). In development, Vite proxies `/api` calls to `http://localhost:5000`.
- **Q3: What happens if the backend server is stopped?**
  - **Answer**: The frontend has an automated fallback mechanism: if the backend server is unreachable, it seamlessly saves and loads assignments from browser `localStorage`.

---

## 📄 License
This project is open-source and created for educational purposes.
