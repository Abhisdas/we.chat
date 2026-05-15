<div align="center">

<h1>💬 we.chat</h1>

<p><strong>A real-time full-stack chat application built with the MERN stack and Socket.IO</strong></p>

<p>
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
  <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" />
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" />
  <img src="https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socket.io&logoColor=white" />
  <img src="https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E" />
</p>

<p>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white" />
  <img src="https://img.shields.io/github/license/Abhisdas/we.chat?style=for-the-badge" />
</p>

</div>

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
  - [Running the App](#running-the-app)
- [Available Scripts](#-available-scripts)
- [Contributing](#-contributing)
- [Author](#-author)
- [License](#-license)

---

## 🚀 About the Project

**we.chat** is a real-time messaging web application built as a monorepo with a decoupled frontend and backend. It enables users to register, log in, and exchange messages instantly with other users — powered by WebSocket technology for a seamless, live communication experience.

This project was built to demonstrate full-stack JavaScript development using the MERN stack, with a focus on real-time bidirectional communication using Socket.IO and a clean React-based user interface scaffolded with Vite.

---

## ✨ Features

- 🔐 **User Authentication** — Secure registration and login with JWT-based session management
- 💬 **Real-Time Messaging** — Instant message delivery using Socket.IO WebSockets
- 👤 **User Profiles** — View and manage user account details
- 🔍 **User Search** — Find and start conversations with other registered users
- 📜 **Message History** — Persistent chat history stored in MongoDB
- 🌐 **Responsive UI** — Clean, responsive interface built with React and Vite
- 🔒 **Protected Routes** — Authenticated access control on both client and server
- ⚡ **Fast Dev Experience** — Vite-powered frontend for lightning-fast HMR and builds

---

## 🛠 Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React.js | UI component library |
| Vite | Build tool and dev server |
| Socket.IO Client | Real-time WebSocket communication |
| React Router DOM | Client-side routing |

### Backend
| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | REST API framework |
| MongoDB + Mongoose | Database and ODM |
| Socket.IO | WebSocket server |
| JSON Web Tokens (JWT) | Authentication |
| bcrypt | Password hashing |

---

## 📁 Project Structure

```
we.chat/
├── backend/                  # Node.js + Express API server
│   ├── controllers/          # Route handler logic
│   ├── middleware/           # Auth middleware, error handlers
│   ├── models/               # Mongoose schemas (User, Message, Chat)
│   ├── routes/               # Express route definitions
│   ├── config/               # DB connection and config
│   ├── server.js             # Entry point — HTTP + Socket.IO server
│   ├── .env                  # Environment variables (not committed)
│   └── package.json          # Backend dependencies
│
├── frontend/                 # React + Vite client
│   ├── public/               # Static assets
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Page-level components (Home, Chat, Login)
│   │   ├── context/          # React context for global state
│   │   ├── hooks/            # Custom React hooks
│   │   ├── utils/            # Helper functions
│   │   ├── App.jsx           # Root component and routing
│   │   └── main.jsx          # Vite entry point
│   ├── index.html
│   └── package.json          # Frontend dependencies
│
├── .gitignore
├── package.json              # Root scripts — build & start orchestration
└── README.md
```

---

## 🏁 Getting Started

### Prerequisites

Make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) `v18+`
- [npm](https://www.npmjs.com/) `v9+`
- [MongoDB](https://www.mongodb.com/) — local instance or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) (free tier)
- [Git](https://git-scm.com/)

---

### Installation

**1. Clone the repository:**

```bash
git clone https://github.com/Abhisdas/we.chat.git
cd we.chat
```

**2. Install all dependencies (backend + frontend):**

```bash
npm run build
```

> This runs `npm install` for both `backend/` and `frontend/` and also builds the React frontend for production.

Alternatively, install each manually:

```bash
# Backend
cd backend && npm install

# Frontend
cd ../frontend && npm install
```

---

### Environment Variables

Create a `.env` file inside the `backend/` directory and add the following variables:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
```

> ⚠️ Never commit your `.env` file. It is already listed in `.gitignore`.

For the frontend, if needed, create a `.env` file inside `frontend/`:

```env
VITE_API_BASE_URL=http://localhost:5000
```

---

### Running the App

**Development mode (run both servers separately):**

Terminal 1 — Start the backend:
```bash
cd backend
npm run dev
```

Terminal 2 — Start the frontend:
```bash
cd frontend
npm run dev
```

The frontend will be available at `http://localhost:5173` and the backend API at `http://localhost:5000`.

**Production mode:**

```bash
# From project root — builds frontend and starts backend
npm run build
npm start
```

---

## 📜 Available Scripts

All scripts are defined in the **root `package.json`**:

| Script | Description |
|---|---|
| `npm run build` | Installs backend & frontend deps, then builds the React frontend |
| `npm start` | Starts the backend Express server in production mode |

Backend-specific scripts (inside `backend/`):

| Script | Description |
|---|---|
| `npm start` | Start server with Node.js |
| `npm run dev` | Start server with Nodemon (hot reload) |

Frontend-specific scripts (inside `frontend/`):

| Script | Description |
|---|---|
| `npm run dev` | Start Vite development server |
| `npm run build` | Build the production-ready frontend |
| `npm run preview` | Preview the production build locally |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add: your feature description'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

Please make sure to update tests and documentation as appropriate.

---

## 👤 Author

**Abhi Das**

- GitHub: [@Abhisdas](https://github.com/Abhisdas)

---

## 📄 License

This project is licensed under the **ISC License** — see the [`package.json`](./package.json) for details.

---

<div align="center">
  <p>If you found this project helpful, consider giving it a ⭐ on <a href="https://github.com/Abhisdas/we.chat">GitHub</a>!</p>
</div>
