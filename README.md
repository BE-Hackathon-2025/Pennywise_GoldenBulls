# Finora AI - Your finances. Automated.*
> Stack: MERN (MongoDB, Express/Node.js, React, TypeScript)

Finora is an AI-driven personal finance and expense management platform that automates transaction entry via receipt scanning, bulk CSV imports and
visualizes insights through MongoDB aggregate pipelines, and delivers monthly email reports.

🚀 Features
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

 🧩 Project Overview

Finora automates financial recordkeeping by combining AI receipt scanning, analytics visualization, and automated reporting. It’s designed for:
Individuals managing personal finances
Freelancers tracking income & expenses
Small businesses seeking lightweight, automated bookkeeping

⚙️ Tech Stack

#Frontend:
React + TypeScript + Chart.js + Axios
#Backend:
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


eact, TypeScript)

