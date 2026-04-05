# FinanceIQ

FinanceIQ is a responsive finance dashboard built with React, TypeScript, Tailwind CSS, Zustand, and Recharts. It is designed as a frontend-only assignment submission that demonstrates dashboard composition, state management, mock financial data handling, role-based UI changes, and clean interaction design.

## What It Covers

- Dashboard overview with balance, income, expense, and transaction summary cards
- Time-based visualization for balance trend
- Category-based visualization for spending breakdown
- Transaction table with search, filtering, and sorting
- Frontend-only role switcher for `Admin` and `Viewer`
- Insights section with key spending observations
- Local persistence for transactions and selected role
- Responsive layout for mobile, tablet, and desktop
- Empty states and export support

## Demo Roles

- `Viewer`: read-only access to dashboard data and insights
- `Admin`: can add, edit, and delete transactions

The role switcher lives in the top navigation so the evaluator can easily test both UI modes.

## Tech Stack

- React 19
- TypeScript
- Vite
- Tailwind CSS v4
- Zustand
- Recharts
- React Router
- date-fns

## State Management

The app uses small, focused Zustand stores:

- `transactionStore`: transaction source of truth with local persistence
- `filterStore`: search, filtering, and sorting state
- `roleStore`: simulated role selection with persistence

Derived metrics such as totals, monthly comparisons, category breakdowns, and insights are calculated in [`src/hooks/useDerivedFinancials.ts`](/C:/Users/K.Saikiran/Downloads/ZORVYN%20FRONTEND%20TASK/ZORVYN%20FRONTEND%20TASK/src/hooks/useDerivedFinancials.ts).

## Running Locally

### Prerequisites

- Node.js `20.19+` or `22.12+`
- npm

### Install

```bash
npm install
```

### Start Development Server

```bash
npm run dev
```

### Validate

```bash
npx tsc -b
npm run lint
npm run build
```

## Notes

- Data is mocked and persisted in `localStorage`
- Currency formatting is shown in INR
- No backend or authentication flow is implemented because the assignment focuses on frontend thinking and execution

## Feature Walkthrough

### Dashboard

- Summary cards for current balance, income, expenses, and transaction count
- Balance trend chart across recent months
- Spending donut chart by category
- Recent transaction snapshot

### Transactions

- Search by description
- Filter by type, category, and date range
- Sort by date or amount
- Admin-only add, edit, and delete flows
- Empty state when filters remove all rows

### Insights

- Highest spending category
- Most frequent category
- Average monthly spend
- Savings rate
- Monthly income versus expense comparison

## Assumptions

- This is a single-user dashboard demo
- Transactions are stored as positive values and interpreted by `income` or `expense` type
- Role behavior is intentionally simulated on the client for demonstration

## Submission Note

On this machine, `npx tsc -b` and `npm run lint` pass. If `npm run build` fails locally, check your Node version first. Vite 8 in this project requires Node `20.19+`, and the current environment I validated in was running Node `20.11.1`, which is too old for the final Vite bundling step.
