# Monarch Investment Platform 🦋

A full-stack hackathon project built in just one week that empowers users to explore stock/crypto data, track performance, and make informed investment decisions with AI-driven insights.

This project was originally deployed on Render during the hackathon but is now fully set up so you can run it locally or host it yourself.

![Dashboard Screenshot](./public/screenshots/Monarch.PNG)

---

## 🚀 Features

- **Frontend:** Modern React app with clean UI
- **Backend:** Node.js/Express API with PostgreSQL database
- **Authentication:** JWT-based auth (configurable in `.env`)
- **Reports:** Generate and download data views (CSV/PDF ready)
- **Data Sync:** Real-time communication with API endpoints
- **Hackathon Scope:** Built in under 7 days and won 🥇

---

## 🛠 Tech Stack

- **Frontend:** React, Vite (or CRA depending on setup), TailwindCSS
- **Backend:** Node.js, Express
- **Database:** PostgreSQL (tested on Neon and Render Postgres)
- **ORM:** Prisma (or Sequelize – check `Boilerplate-Backend/package.json`)
- **Deployment:** Render (backend) + Vercel (frontend)

---

## 📂 Project Structure

```
Hackathon-Project/
│
├── Boilerplate-Backend/    # Node.js + Express API
│   ├── src/
│   ├── prisma/ or migrations/
│   └── package.json
│
├── src/ (or frontend code) # React application
├── public/
├── package.json
└── README.md
```

---

## 📸 Screenshots

### Mobile
![1](./public/screenshots/Monarch1.PNG)
![2](./public/screenshots/Monarch2.PNG)
![3](./public/screenshots/Monarch3.PNG)

---

## ⚡ Getting Started

### 1. Clone Repo
```bash
git clone https://github.com/falvarado7/Hackathon-Project.git
cd Hackathon-Project
```

### 2. Setup Backend
```bash
cd Boilerplate-Backend
npm install
cp .env.example .env   # create your .env
```

Fill in `.env` with values like:
```
DATABASE_URL=postgresql://user:password@host:5432/dbname?sslmode=require
JWT_SECRET=supersecret
CORS_ORIGIN=http://localhost:5173
PORT=4000
```

Run migrations:
```bash
# Prisma
npx prisma generate
npx prisma migrate deploy

# OR Sequelize
npx sequelize-cli db:migrate
npx sequelize-cli db:seed:all
```

Start the backend:
```bash
npm run dev
```

### 3. Setup Frontend
From repo root:
```bash
npm install
```

Set your API URL:
- Vite: create `.env` and add
  `VITE_API_URL=http://localhost:4000`
- CRA: use
  `REACT_APP_API_URL=http://localhost:4000`

Run:
```bash
npm run dev   # or npm start
```

Frontend runs on **http://localhost:5173** (Vite) or **http://localhost:3000** (CRA).

---

## 🌐 Deployment

- **Backend:**
  Deploy `Boilerplate-Backend` as a **Web Service** on [Render](https://render.com).
  Set `DATABASE_URL`, `JWT_SECRET`, and `CORS_ORIGIN` in the environment.

- **Frontend:**
  Deploy root app to [Vercel](https://vercel.com) or as a Render Static Site.
  Be sure to set `VITE_API_URL` (or `REACT_APP_API_URL`) to your backend URL.

---

## ✅ To Do / Improvements

- Add robust error handling for API calls
- Strengthen auth flow (refresh tokens, password reset)
- Containerize with Docker for easier deployment
- Expand AI insights with more datasets
- Write unit + integration tests
