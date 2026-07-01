# ⚡ New Royal ERP — Billing & Inventory Management System

> **New Royal Electricals & Hardware** | 92, Main Road, Pennadam – 606 105 | GSTIN: 33AACFN4722E1ZR

A production-grade, full-stack ERP system for billing, inventory, and business management. Built with Next.js, Express.js, MongoDB Atlas, Electron (Windows), and React Native (Android/iOS).

---

## 🗂️ Project Structure

```
new-royal-erp/
├── packages/
│   └── api/              # Express.js Backend API (Node.js + MongoDB)
└── apps/
    ├── web/              # Next.js 14 Admin Panel (Vercel)
    ├── desktop/          # Electron Windows Desktop App
    └── mobile/           # React Native / Expo (Android + iOS)
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- MongoDB Atlas account (you have your connection string)
- npm 9+

### Step 1 — Configure Environment

**Backend API (`packages/api/.env`):**
```bash
cp packages/api/.env.example packages/api/.env
```
Edit `packages/api/.env` and add your MongoDB URI:
```
MONGODB_URI=mongodb+srv://YOUR_USERNAME:YOUR_PASSWORD@YOUR_CLUSTER.mongodb.net/new-royal-erp
```

**Web App (`apps/web/.env.local`):**
```bash
cp apps/web/.env.local.example apps/web/.env.local
```

### Step 2 — Install Dependencies

```bash
# Install all packages (from root)
cd packages/api && npm install
cd ../../apps/web && npm install
```

### Step 3 — Seed the Database

```bash
cd packages/api
npm run seed
```
This creates:
- Admin user: `admin` / `Admin@123`
- Staff user: `staff` / `Staff@123`
- Default business settings
- 20 sample products
- 5 sample customers

### Step 4 — Start Development

**Terminal 1 — Backend API:**
```bash
cd packages/api
npm run dev
# Runs on http://localhost:5000
```

**Terminal 2 — Web Admin Panel:**
```bash
cd apps/web
npm run dev
# Runs on http://localhost:3000
```

Open `http://localhost:3000` → Login with `admin` / `Admin@123`

---

## 🌐 Deployment (Vercel + Render)

### Backend API → Render (Free)

1. Push project to GitHub
2. Go to [render.com](https://render.com) → New Web Service
3. Connect GitHub repo → select `packages/api` as root dir
4. Build command: `npm install`
5. Start command: `npm start`
6. Add all environment variables from `.env.example`

### Web Frontend → Vercel

1. Go to [vercel.com](https://vercel.com) → New Project
2. Connect GitHub repo → select `apps/web` as root dir
3. Set `NEXT_PUBLIC_API_URL` = your Render API URL

---

## 🖥️ Windows Desktop App

```bash
cd apps/desktop
npm install
npm run dev    # Development mode (requires web app on :3000)
npm run build  # Creates Windows installer (.exe)
```

---

## 📱 Mobile App (Android & iOS)

```bash
cd apps/mobile
npm install
npm run start   # Expo dev server
npm run android # Android emulator
npm run ios     # iOS simulator (Mac only)
```

Configure API URL in `apps/mobile/app.json`:
```json
"extra": { "apiUrl": "https://your-api.onrender.com" }
```

---

## 🔐 Login Credentials (After Seeding)

| Role | Username | Password |
|------|----------|----------|
| Admin | `admin` | `Admin@123` |
| Staff | `staff` | `Staff@123` |

---

## 📦 Features

### ✅ Billing & Invoicing
- POS-style billing with barcode scan support
- GST calculation (CGST + SGST)
- Multiple payment methods (Cash, Card, UPI, Cheque)
- PDF invoice generation (A4 + Thermal 80mm)
- WhatsApp sharing
- Email invoices

### ✅ Inventory Management
- Full product CRUD with images
- Barcode/QR code support
- Stock tracking with history
- Excel import/export
- Low stock alerts
- Batch and expiry date tracking

### ✅ Quotation System
- Professional quotations with expiry
- Convert quotation → Invoice in one click
- PDF + WhatsApp sharing

### ✅ Customer & Vendor Management
- Customer CRM with purchase history
- Outstanding payments tracking
- Vendor management with PO history

### ✅ Reports
- Daily/Weekly/Monthly/Yearly sales
- GST reports (CGST, SGST)
- Profit & Loss statement
- Inventory valuation
- Product-wise sales
- Export: PDF + Excel

### ✅ Dashboard
- Real-time KPI cards
- Sales area chart (30 days)
- Monthly revenue bar chart
- Best selling products
- Low stock alerts
- Recent invoices & quotations

### ✅ Security
- JWT authentication (15min + 7-day refresh)
- Role-based access (Admin/Staff)
- Password encryption (bcrypt)
- Rate limiting
- Helmet security headers
- Audit activity logs

### ✅ Settings
- Business info management
- Invoice prefix & numbering
- GST rate configuration
- Printer settings (A4 / Thermal 80mm)
- Email SMTP configuration
- Theme customization

---

## 🎨 Design System

| Token | Value | Usage |
|-------|-------|-------|
| `--gold` | `#C8922A` | Primary brand color |
| `--dark` | `#0D0F14` | App background |
| `--surface` | `#1A1F2E` | Card/panel background |
| `--text` | `#F0EDE6` | Primary text |
| `--green` | `#2ECC71` | Success/In Stock |
| `--red` | `#E74C3C` | Error/Out of Stock |

---

## 📞 Support

**New Royal Electricals & Hardware**  
92, Main Road, Pennadam – 606 105  
GSTIN: 33AACFN4722E1ZR | Est. 1970

---

*Built with ❤️ for New Royal Electricals*
