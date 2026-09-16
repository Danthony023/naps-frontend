<div align="center">
  <img src="./src/assets/images/NAPS_LOGO.jpeg" alt="NAPS Logo" width="160" />

  <h1>NAPS Frontend</h1>
  <p><strong>Nigerian Association of Physics Students — Student Portal</strong></p>

  <p>
    <img src="https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white&style=flat-square" alt="React 18" />
    <img src="https://img.shields.io/badge/Vite-6-646CFF?logo=vite&logoColor=white&style=flat-square" alt="Vite 6" />
    <img src="https://img.shields.io/badge/TailwindCSS-3-06B6D4?logo=tailwindcss&logoColor=white&style=flat-square" alt="TailwindCSS" />
    <img src="https://img.shields.io/badge/Deployed-Vercel-000000?logo=vercel&logoColor=white&style=flat-square" alt="Vercel" />
  </p>
</div>

---

## 📖 Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running Locally](#running-locally)
  - [Building for Production](#building-for-production)
- [Environment Variables](#environment-variables)
- [API Overview](#api-overview)
- [Testing](#testing)
- [Deployment](#deployment)
- [Contributing](#contributing)

---

## 🎓 About the Project

**NAPS Frontend** is the official web portal for the **Nigerian Association of Physics Students (NAPS)**. It provides students with a centralised platform to access academic resources, connect with mentors, participate in discussions, track upcoming events, and manage their student profiles — all in one place.

The application is built as a **React + Vite** single-page application (SPA) and communicates with a dedicated REST API backend secured with API keys and JWT authentication.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔐 **Authentication** | Register, log in (email or matric number), verify email via OTP, forgot/reset password |
| 🧑‍💼 **Profile Management** | View and update your student profile, upload profile picture and departmental fees receipt |
| 📚 **Academic Resources** | Browse and download study materials filtered by level; upload new resources (pending admin approval) |
| 📅 **Upcoming Events** | View, RSVP, and cancel RSVPs for departmental and association events |
| 🤝 **Mentor Programme** | Apply for mentorship, apply to become a mentor, and view your assigned mentor |
| 💬 **Forums** | Participate in department-wide discussion threads, post topics and replies in real time |
| 📊 **Dashboard** | Personalised overview of activity, quick-access widgets, and statistics |

---

## 🛠 Tech Stack

### Core
- **[React 18](https://react.dev/)** — UI library
- **[Vite 6](https://vitejs.dev/)** — Build tool & dev server
- **[React Router DOM v7](https://reactrouter.com/)** — Client-side routing

### Styling & UI
- **[Tailwind CSS 3](https://tailwindcss.com/)** — Utility-first CSS framework
- **[Radix UI](https://www.radix-ui.com/)** — Accessible, headless UI primitives (Alert Dialog, Dropdown Menu, Label, Select)
- **[MUI (Material UI) v6](https://mui.com/)** — Supplementary component library
- **[Framer Motion](https://www.framer.com/motion/)** — Page and element animations
- **[Lucide React](https://lucide.dev/)** & **[React Icons](https://react-icons.github.io/react-icons/)** — Icon sets

### Data & Communication
- **[Axios](https://axios-http.com/)** — HTTP client for API calls
- **[Socket.IO Client](https://socket.io/docs/v4/client-api/)** — Real-time communication (Forums)

### Utilities
- **[SweetAlert2](https://sweetalert2.github.io/)** — Elegant alert and confirmation dialogs
- **[Add to Calendar Button](https://add-to-calendar-button.com/)** — Event calendar integration
- **[clsx](https://github.com/lukeed/clsx)** & **[tailwind-merge](https://github.com/dcastil/tailwind-merge)** — Conditional class name utilities

### Testing
- **[Vitest](https://vitest.dev/)** — Unit test runner
- **[Testing Library (React)](https://testing-library.com/)** — Component testing utilities
- **[MSW](https://mswjs.io/)** — API mocking for tests

---

## 🗂 Project Structure

```
naps-frontend/
├── public/
│   └── NAPS_LOGO.png             # App icon / favicon
├── src/
│   ├── apiCalls/                 # Axios API call functions grouped by feature
│   ├── assets/
│   │   ├── fonts/                # Custom fonts
│   │   └── images/               # Static images and icons
│   ├── components/               # Reusable UI components
│   │   ├── Dashboard/
│   │   ├── Forums/
│   │   └── resources/
│   ├── context/
│   │   └── AuthContext.jsx       # Global authentication context & provider
│   ├── layouts/
│   │   └── DashboardLayout.jsx   # Shared layout for all authenticated pages
│   ├── lib/                      # Utility helpers
│   ├── pages/
│   │   ├── authentication/       # Login, Signup, ForgotPassword, ResetPassword, VerifyAccount
│   │   ├── Dashboard.jsx
│   │   ├── Forums.jsx
│   │   ├── MentorProgram.jsx
│   │   ├── MyMentor.jsx
│   │   ├── Resources.jsx
│   │   ├── upcomingEvents.jsx
│   │   ├── profileOverview.jsx
│   │   └── Welcome.jsx
│   ├── services/                 # Shared service modules (e.g., socket service)
│   ├── test/                     # Test files and MSW handlers
│   ├── App.jsx                   # Root component with all route definitions
│   └── main.jsx                  # Application entry point
├── index.html                    # HTML shell
├── vite.config.js                # Vite configuration
├── tailwind.config.js            # Tailwind CSS configuration
├── vercel.json                   # Vercel SPA rewrite rules
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- **Node.js** ≥ 18.x — [Download](https://nodejs.org/)
- **npm** ≥ 9.x (ships with Node.js)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-org>/naps-frontend.git
   cd naps-frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables** — see [Environment Variables](#environment-variables) below.

### Running Locally

```bash
npm run dev
```

The app will start at **[http://localhost:5173](http://localhost:5173)** by default.

### Building for Production

```bash
npm run build
```

The optimised output is placed in the `dist/` directory. To preview it locally:

```bash
npm run preview
```

---

## 🔑 Environment Variables

Create a `.env` file in the project root and populate it as follows:

```env
# Base URL of the NAPS backend API
VITE_API_BASE_URL=https://your-api-domain.com/api

# API Key for authenticating requests to the backend
VITE_API_KEY=your-api-key-here
```

> **Important:** All Vite environment variables must be prefixed with `VITE_` to be accessible inside the browser bundle. Never commit your `.env` file to version control — add it to `.gitignore`.

---

## 🌐 API Overview

The frontend communicates with a RESTful backend API. Most requests require the following headers:

| Header | Value |
|---|---|
| `X-API-Key` | Your project API key |
| `Authorization` | `Bearer <jwt-token>` (required for protected routes) |

**Base URL:** `https://your-api-domain.com/api`

### Modules

| Module | Base Path | Description |
|---|---|---|
| Authentication | `/users` | Register, login, OTP verification, password reset |
| User Profile | `/users/me`, `/users/update/{id}` | Fetch and update the current user's profile |
| Resources | `/api/resources` | Upload, browse, approve, and delete study materials |
| Events | `/api/events` | List, create, RSVP, and cancel RSVPs for events |
| Mentorship | `/api/mentorship` | Apply for mentorship, manage mentor assignments |
| Forums | `/api/forum` | Create posts, reply to threads, browse topics |

> For the full route reference including request bodies and response shapes, see [`backend_api_gap_analysis.txt`](./backend_api_gap_analysis.txt).

---

## 🧪 Testing

Run the full test suite:

```bash
npm test
```

Run tests with a coverage report:

```bash
npm run test:coverage
```

Test files live in `src/test/`. API calls are mocked using **MSW (Mock Service Worker)**, so tests run without a live backend connection.

---

## ☁️ Deployment

This project is configured for **[Vercel](https://vercel.com/)** deployment. The [`vercel.json`](./vercel.json) file ensures all client-side routes are rewritten to `index.html` for correct SPA behaviour.

**To deploy:**

1. Push your changes to the main branch (if using Vercel's Git integration), **or**
2. Use the Vercel CLI:
   ```bash
   npx vercel --prod
   ```

Set `VITE_API_BASE_URL` and `VITE_API_KEY` as environment variables in your Vercel project settings before deploying.

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/your-feature-name`
3. **Commit** your changes: `git commit -m "feat: describe your change"`
4. **Push** to your fork: `git push origin feature/your-feature-name`
5. **Open a Pull Request** with a clear description of your changes

Please use conventional commit prefixes (`feat:`, `fix:`, `chore:`, `docs:`, etc.) and ensure all tests pass before submitting your PR.

---

<div align="center">
  <sub>Built with ❤️ by the NAPS Dev Team</sub>
</div>
