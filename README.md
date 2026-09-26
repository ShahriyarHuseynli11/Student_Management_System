# 🎓 Student Management System

A Node.js/Express web application scaffold for managing students, with session-based authentication and role support. It's set up to use **MySQL** for core data and **MongoDB** for logging.

> ⚠️ **Status: early scaffold.** The folder structure and dependencies are in place, but most files (routes, controllers, models, middleware, views, DB config) are currently **empty placeholders**. Only `app.js` has working code so far — it starts an Express server with sessions and EJS configured, and serves a single test route. See [Roadmap](#-roadmap--todo) below for what's left to build.

## 🛠️ Tech stack

| Layer | Technology |
|---|---|
| Runtime / Framework | Node.js, Express 5 |
| View engine | EJS |
| Databases | MySQL (`mysql2`), MongoDB (`mongoose`) |
| Auth | `express-session`, `bcrypt` |
| Validation | `express-validator` |
| Dev tooling | `nodemon` |

## 📁 Project structure

```
├── app.js                        # Express entry point (currently the only working part)
├── config/
│   ├── mysql.js                  # (empty) intended: MySQL connection setup
│   └── mongo.js                  # (empty) intended: MongoDB connection setup
├── controllers/
│   ├── auth.controller.js        # (empty) intended: login/logout logic
│   └── student.controller.js     # (empty) intended: student CRUD logic
├── middleware/
│   ├── auth.middleware.js        # (empty) intended: session/login guard
│   └── role.middleware.js        # (empty) intended: role-based access control
├── models/
│   ├── user.model.js             # (empty) intended: user schema/model
│   └── student.model.js          # (empty) intended: student schema/model
├── routes/
│   ├── auth.routes.js            # (empty) intended: auth endpoints
│   └── student.routes.js         # (empty) intended: student endpoints
├── views/
│   ├── login.ejs                 # (empty)
│   ├── dashboard.ejs             # (empty)
│   └── student/
│       ├── list.ejs              # (empty)
│       ├── add.ejs               # (empty)
│       └── edit.ejs              # (empty)
└── public/css/style.css          # (empty)
```

## ⚙️ Setup

```bash
git clone <this-repo-url>
cd student-management-system

npm install

# create your local environment file
cp .env.example .env
# then edit .env with your own MySQL/MongoDB credentials and session secret

npm run dev     # if a "dev" script is added (nodemon), or:
node app.js
```

The server currently starts on **http://localhost:3000** and responds with a plain "Student Management System işləyir ✅" test message at `/`.

## 🔑 Environment variables

Copy `.env.example` to `.env` and fill in real values — `.env` is git-ignored and should never be committed.

| Variable | Purpose |
|---|---|
| `PORT` | Port the Express server listens on |
| `SESSION_SECRET` | Secret used to sign session cookies |
| `DB_HOST`, `DB_USER`, `DB_PASS`, `DB_NAME` | MySQL connection details |
| `MONGO_URI` | MongoDB connection string (used for logging) |

## 🗺️ Roadmap / TODO

- [ ] Implement MySQL connection in `config/mysql.js`
- [ ] Implement MongoDB connection in `config/mongo.js`
- [ ] Build authentication: `auth.controller.js`, `auth.routes.js`, `auth.middleware.js`
- [ ] Implement role-based access in `role.middleware.js`
- [ ] Define `user.model.js` and `student.model.js`
- [ ] Implement student CRUD in `student.controller.js` and `student.routes.js`
- [ ] Build out the EJS views (`login`, `dashboard`, `student/list`, `student/add`, `student/edit`)
- [ ] Mount the auth and student routers in `app.js` (they aren't wired up yet)
- [ ] Add basic styling in `public/css/style.css`

## ⚠️ Notes

- `node_modules/` and `.env` are excluded via `.gitignore` — never commit real secrets.
- The `.env` values in the original project (e.g. `DB_PASS=1234`) were local dev placeholders; use your own credentials via `.env`.
