# AI-Powered Smart Restaurant Automation System
### Implementation Plan 

A full-stack, AI-enhanced hospitality management platform built as a single integrated web application covering guest ordering, kitchen display, billing, inventory, staff ERP, and business intelligence analytics.

---

## 🏗️ Architecture & Technology Stack

| Layer | Technology | Details |
|---|---|---|
| **Frontend** | React + Vite (SPA) | Component-based, responsive UI |
| **Styling** | Vanilla CSS + CSS Variables | Luxury dark glassmorphism theme, frosted glass cards, gold (`#f59e0b`) & emerald (`#10b981`) accents |
| **State Management** | React Context + Hooks | `AuthContext`, `CartContext`, `OrderContext` |
| **Backend / API** | Node.js + Express | REST API covering Menu, Orders, Billing, Inventory, Staff ERP, Analytics, Tables |
| **Database** | SQLite (via `sqlite3`) | Zero-config, persistent, file-based schema with foreign keys and seed data |
| **Real-time Engine** | Socket.IO | Bi-directional WebSockets for live KDS order updates, table statuses & waiter alerts |
| **AI / Voice** | Web Speech API | Multi-lingual voice ordering in **Hindi (`hi-IN`)**, **Marathi (`mr-IN`)**, and **English (`en-IN`)** |
| **AI Upsell Engine** | Rule-based Pairing Engine | Contextual combo recommendations based on cart contents (e.g. curry → naan; biryani → lassi/cooler) |
| **Audio Alert Engine** | Web Audio API Synth | Synthesized chime alerts for kitchen tickets and waiter calls without external dependencies |
| **Payments (Simulated)** | Dynamic UPI QR + Razorpay | Dynamic UPI QR code generator, Razorpay test mode sandbox, and cash/card toggle |
| **BI Visualizations** | Chart.js + react-chartjs-2 | Interactive line, bar, and doughnut charts |

---

## 👥 User Roles & Portals

| Role | Portal / Interface | Primary Features |
|---|---|---|
| **Guest Diner** | Table Ordering Interface | Touch & Voice digital menu, dietary filter tags (Veg, Non-Veg, Vegan, Gluten-Free), spice levels, allergy notes, real-time cart, AI combo upsells, live order status tracker (Received → Preparing → Ready → Served), Call Waiter button |
| **Kitchen Staff** | Kitchen Display System (KDS) | Live WebSocket order feed, urgency color-coding (Green < 5m, Yellow 5-15m, Red > 15m), live elapsed timers, item cooking checklist, status progression (Accept → Preparing → Ready → Served) |
| **Floor Staff / Waiter** | Table Management App | 10 dining tables live occupancy grid, running order totals, quick order assist, waiter service alert resolution |
| **Cashier / POS Host** | POS & Billing Center | Auto-generated GST bill (2.5% CGST + 2.5% SGST), discount coupons (`WELCOME10`, `CHEF20`, `FLAT50`), bill split calculator, print-ready thermal receipt view, payment logs |
| **Store Manager** | Inventory Management (BOM) | Ingredient-level stock tracking, automated Bill of Materials (BOM) deduction on order confirmation, low-stock threshold alerts, restock & wastage logs, CSV export |
| **HR / Floor Manager** | Staff ERP & Attendance | Staff profiles, attendance clock-in / clock-out timestamping, shift rota calendar, performance-based payroll summary |
| **Owner / Director** | Executive BI Dashboard | KPI cards (Today's Revenue, Total Revenue, AOV, Table Occupancy), 7-day revenue trend line chart, category doughnut chart, peak hours bar chart, top sellers leaderboard, staff performance |

---

## 🔑 Pre-seeded Demo Credentials & 1-Click Role Switcher

For seamless evaluation, use the **Role Switcher dropdown** in the header to switch between roles in 1 click, or sign in using:

| Role | Email | Password |
|---|---|---|
| **Owner** | `owner@gc17.com` | `admin123` |
| **Manager** | `manager@gc17.com` | `admin123` |
| **Head Chef (KDS)** | `kitchen@gc17.com` | `chef123` |
| **Floor Captain / Staff** | `staff@gc17.com` | `staff123` |
| **Guest Diner** | `guest@gc17.com` | `admin123` (or direct table access) |

---

## 🚀 Running Locally

### 1. Backend Server
```bash
cd backend
npm install
node database/seed.js   # Seeds database with tables, menu, ingredients, BOM recipes
npm start               # Runs Express & Socket.IO server on http://localhost:5000
```

### 2. Frontend Web Application
```bash
cd frontend
npm install
npm run dev             # Starts Vite dev server on http://localhost:5173
```

Access the app in your browser at: **`http://localhost:5173/`**
