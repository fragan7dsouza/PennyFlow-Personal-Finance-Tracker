# 💸 PennyFlow - Personal Finance Tracker

A clean, minimal **React and TypeScript web application** designed for effortless personal finance tracking.
Built with **Vite, React (TSX), and Tailwind CSS (shadcn/ui)**, and powered by **Supabase** for robust authentication and database management.

-----

## ⚙️ Features

  - ✅ **Secure Authentication (`/`)**

      - Users can **Sign Up** and **Sign In** to their personal account.
      - Routes are protected, requiring authentication to access main features.

  - ✅ **Dashboard Overview (`/dashboard`)**

      - View real-time financial summaries for the current month: **Total Income, Total Expenses, and Net Balance**.
      - Visualize spending with interactive charts, including **Expenses by Category** and **Income vs Expenses**.

  - ✅ **Transaction Management (`/transactions`)**

      - Perform **CRUD operations** (Add, Edit, Delete) on all income and expense records.
      - Easily filter and search transactions by category, type (income/expense), and date range.

  - ✅ **Category Management (`/categories`)**

      - Create, view, edit, and delete custom categories for organizing transactions, each with a unique color.

-----

## 🧩 Technical Overview

### 🏗️ Architecture Layers

| Layer | Files/Components | Description |
| :---- | :---------------- | :----------- |
| **Presentation (UI)** | `src/components/ui/*` | Custom components using shadcn/ui and Radix Primitives for a consistent interface. |
| **View (Pages)** | `src/pages/*` | Defines the main application views (e.g., Dashboard, Transactions, Auth). |
| **Logic/Routing** | `src/App.tsx`, `react-router-dom` | Manages component routing, state containers, and core feature logic. |
| **Data/Auth Service** | `src/integrations/supabase/client.ts` | Centralized Supabase client for all database and authentication interactions. |

-----

## 📁 Project Structure

```
PennyFlow-Personal-Finance-Tracker/
│
├── src/
│   ├── components/
│   │   ├── ui/      (UI components: Button, Card, Table, etc.)
│   │   ├── Layout.tsx
│   │   ├── ProtectedRoute.tsx
│   │   ├── TransactionModal.tsx
│   │   └── ...
│   │
│   ├── hooks/
│   │   └── use-toast.ts
│   │
│   ├── integrations/supabase/
│   │   └── client.ts
│   │
│   ├── pages/
│   │   ├── Auth.tsx
│   │   ├── Dashboard.tsx
│   │   ├── Transactions.tsx
│   │   └── Categories.tsx
│   │
│   └── App.tsx
│
├── supabase/
│   └── migrations/
│       └── 20251114090507_...sql (Database schema)
│
├── .env
├── package.json
└── README.md
```

-----

## ⚙️ Setup & Configuration

### 1️⃣ Supabase Database Setup

The project is configured to use two primary tables, which should be set up in your Supabase project (Project ID: `czseqghbzfmfwsbrytab`):

1.  **`categories`**: Stores user-defined categories with an assigned color.
2.  **`transactions`**: Stores financial entries (income/expense) linked to a user and a category.

The necessary tables and Row Level Security (RLS) policies, including a trigger to auto-seed default categories for new users, are defined in the SQL migration file.

### 2️⃣ Environment Variables

Configure your project by creating a `.env` file in the root directory with your Supabase credentials.

```
# Supabase Project ID is already set in supabase/config.toml
VITE_SUPABASE_PROJECT_ID="czseqghbzfmfwsbrytab"
# Replace with your actual public key and URL
VITE_SUPABASE_PUBLISHABLE_KEY="eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImN6c2VxZ2hiemZtZndzYnJ5dGFiIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NjMwODQ5OTMsImV4cCI6MjA3ODY2MDk5M30.U10P1bT_Nvm4mgv0PtioMete7tsjfrgF9oq2ysX0-cA"
VITE_SUPABASE_URL="https://czseqghbzfmfwsbrytab.supabase.co"
```

### 3️⃣ Installation

Install the required dependencies using npm or yarn:

```sh
npm install
# or
yarn install
```

-----

## 🚀 Deployment

This project uses **Vite** for its build process.

**Start the development server:**

```sh
npm run dev
```

Access in browser: `http://localhost:8080` (or the URL provided by Vite).

**Build for production:**

```sh
npm run build
```

-----

## 💡 Example Usage

### 🔐 Initial Access

  * Go to the homepage (`/`)
  * **Sign Up** with a new email and password
  * You will be redirected to the **Sign In** tab to log in

### ➕ Add a Transaction

  * Navigate to **Transactions** (`/transactions`).
  * Click **"Add Transaction"**.
  * Enter **Amount**, select **Type** (Income/Expense), choose a **Category**, and set the **Date**.

### 📊 View Financial Summary

  * Navigate to **Dashboard** (`/dashboard`).
  * See immediate updates to your Total Income, Expenses, and Net Balance for the current month.

-----

## 📌 Notes

  * Authentication and database persistence are handled by **Supabase**.
  * The UI is built with **Tailwind CSS** utility classes and custom components (shadcn/ui flavor).
  * The application uses client-side routing with `react-router-dom`.

-----

## 👨‍💻 Author

**Fragan Dsouza**

📎 [LinkedIn](https://linkedin.com/in/fragan-dsouza)
💻 [GitHub](https://github.com/fragan7dsouza)

-----

## 📜 License

This project is **open-source** and free to use under the **MIT License**.
