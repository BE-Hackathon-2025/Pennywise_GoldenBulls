# Finora AI - Your finances. Automated.
> Stack: MERN (MongoDB, Express/Node.js, React, TypeScript)

Finora is an AI-driven personal finance and expense management platform that automates transaction entry via receipt scanning, bulk CSV imports and
visualizes insights through MongoDB aggregate pipelines, and delivers monthly email reports.

#🚀 Features
🔐 Authentication:Secure Email + Password with JWT
🏢 Transactions: Create, edit, duplicate, and bulk import and  delete
📤Receipt AI: Upload & auto-scan receipts (extract amount, date, merchant)
📈 Analytics: MongoDB aggregations for income & expense summaries
🥧Expense Breakdown Pie Chart
📈 Income vs Expense Line Chart
📅 Date Filters: Last 7/30/90 days, This Month, Custom range
♻️ Recurring Transactions: Automated with Cron Jobs
📄Monthly Reports: Auto-generated and emailed to users
📥 CSV Import: Upload and import transactions in bulk
🔍Filter & Search with pagination and sorting
🗑️ Bulk Delete for cleanup
➕ Duplicate Transactions for re-use
🧑‍💼 Profile Photo Upload: Cloudinary integration
🌐 Built With: MERN Stack (Node.js, MongoDB, React, TypeScript)

# 🧩 Project Overview

Finora automates financial recordkeeping by combining AI receipt scanning, analytics visualization, and automated reporting. It’s designed for:
Individuals managing personal finances
Freelancers tracking income & expenses
Small businesses seeking lightweight, automated bookkeeping

#⚙️ Tech Stack

Frontend:
React + TypeScript + Chart.js + Axios
Backend:
Node.js + Express + TypeScript
Database:
MongoDB (Mongoose)
AI: OCR (Google Vision) for receipt scanning
File Storage: Cloudinary for profile photos & receipts
Email: Nodemailer / SMTP for monthly reports
Scheduler:node-cron for recurring tasks

## 🧠 Architecture

```text
[React Client] ⇄ [Express API] ⇄ [MongoDB]
                 ↘︎ [Cloudinary]
                 ↘︎ [OCR Provider]
                 ↘︎ [Email/SMTP]
```


## 🗂️ Folder Structure

```
finora/
├─ client/               # React + TypeScript frontend
│  ├─ src/
│  │  ├─ features/       # Auth, Transactions, Reports
│  │  ├─ components/     # Reusable UI
│  │  ├─ api/            # Axios setup / RTK Query
│  │  ├─ hooks/          # Custom hooks
│  │  ├─ store/          # Redux store
│  │  └─ pages/          # Page routes
│
└─ server/               # Node.js + Express backend
   ├─ src/
   │  ├─ modules/        # Auth, Transactions, Reports, Receipts, Analytics
   │  ├─ middlewares/    # Auth, error, rate limit
   │  ├─ config/         # Env, Cloudinary, Email
   │  ├─ utils/          # Helpers, CSV, date, validation
   │  └─ app.ts          # Express app setup
   └─ index.ts           # Entry point
```


## 🔧 Setup Instructions

### 1. Clone & Install

```bash
git clone https://github.com/yourusername/finora.git
cd finora
cd server && npm install
cd ../client && npm install
```

### 2. Environment Variables

Create a `.env` file in `server/`:

```env
PORT=4000
MONGO_URI=mongodb://localhost:27017/finora
JWT_SECRET=super_secret
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_key
CLOUDINARY_API_SECRET=your_secret
SMTP_HOST=smtp.example.com
SMTP_USER=no-reply@finora.app
SMTP_PASS=password
```

### 3. Run Locally

```bash
# Backend
dcd server && npm run dev

# Frontend
cd client && npm start
```

---

## 📊 Example Mongo Aggregations

**Expense Breakdown by Category:**

```js
Transactions.aggregate([
  { $match: { type: 'expense', userId } },
  { $group: { _id: '$category', total: { $sum: '$amount' } } },
  { $sort: { total: -1 } }
])
```

Income vs Expense Trend:

```js
Transactions.aggregate([
  { $match: { userId, date: { $gte: start, $lte: end } } },
  { $group: {
      _id: { month: { $month: '$date' }, type: '$type' },
      total: { $sum: '$amount' }
  } }
])
```



## 🤖 AI Receipt Scanning Flow

1. User uploads a photo of a receipt.
2. Finora runs OCR via Tesseract/Google Vision.
3. Extracted data → parsed into `{ amount, date, merchant, category }`.
4. User confirms → transaction auto‑created.

---

## 🔁 Recurring Transactions

* Configurable via cron jobs.
* Auto‑creates transactions for monthly or weekly bills.
* Logs execution timestamps for next run.

---

## 📨 Monthly Report Automation

* Cron runs monthly on the 1st.
* Aggregates user data for the previous month.
* Generates a PDF/HTML summary.
* Sends via email with top categories and trends.

---

## 🧾 CSV Import

Upload a `.csv` with the following format:

```
Date,Type,Amount,Currency,Category,Merchant,Note
2025-11-01,expense,12.99,USD,Food,Uber Eats,Lunch
2025-11-02,income,1200,USD,Salary,Acme Inc.,November paycheck
```

---

## 🔒 Security

* JWT‑based auth (access + refresh)
* Bcrypt password hashing
* Helmet, rate limiting, and input validation
* HTTPS in production

---

## 🧪 Testing

* **Unit:** Jest for backend services
* **Integration:** Supertest for API endpoints
* **E2E:** Cypress/Playwright for frontend UI



## ☁️ Deployment

* Dockerized build for both client and server
* Environment‑specific configs** via `.env`
* CI/CD ready for AWS, Render, or Vercel
* PM2 / Nginx for process & proxy management


## 🗺️ Roadmap

* Budget planning tools
* Multi‑user workspaces
* AI‑based expense categorization
* Mobile app (React Native)
* Bank sync integrations (Plaid)



## 💡 Credits

Built with ❤️ by H_M
© 2025 Finora AI. All rights reserved.

