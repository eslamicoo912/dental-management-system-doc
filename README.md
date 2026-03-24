# 🦷 Dental Clinic Management System (SRS)

A comprehensive Software Requirements Specification (SRS) and project overview for a modern, full-stack Dental Clinic Management System. Built with the MERN stack (MongoDB, Express, React, Node.js) and strictly typed with TypeScript.

[![Youtube Video](https://img.shields.io/badge/Youtube-Video-red?style=for-the-badge)](https://youtu.be/at04SHIci6Q)

## 1. Project Overview
This system is designed to streamline dental clinic operations, reduce patient no-shows through proactive follow-ups, and provide real-time visibility into clinic performance and inventory.

## 2. Core Business Problems Solved
*   **Patient Retention**: Automates the recall process to ensure patients return for routine checkups and treatment continuations.
*   **Operational Efficiency**: Replaces manual paper queues with a real-time digital waiting list.
*   **Financial Transparency**: Tracks outstanding payments and provides detailed growth analytics per staff/treatment.
*   **Inventory Control**: Monitors surgical supply consumption linked directly to patient examinations.

## 3. Functional Requirements (Modules)

### 3.1 Patient Management
*   Full patient registration and searchable history.
*   360-degree view of patient interactions including past examinations, payments, and follow-up logs.
*   Remaining balance tracking per patient.

### 3.2 Visual Dental Chart
*   Visual representation of teeth and their status.
*   Ability to add treatments to specific teeth.
*   Track treatment history for each tooth.

### 3.3 Real-time Queue Management
*   Live waiting list with status transitions (Waiting, In-Progress, Finished).
*   Automatic reordering and schedule break management.
*   Visual indicators for "In-Progress" sessions.

### 3.4 Examination & Treatment Tracking
*   Multi-treatment examination sessions.
*   Partial payment handling and outstanding balance calculation.
*   Note-taking and doctor observations per visit.

### 3.5 Proactive Recall & Follow-up System
*   **Automated Recall Generation**: Based on predefined intervals (e.g., 6 months cleaning, 3 days follow-up).
*   **Master-Detail Queue**: High-performance dashboard for staff to manage outbound calls.
*   **Contact History Timeline**: Full audit log of every communication attempt (Phone, WhatsApp) with outcomes.
*   **Proactive Notifications**: Pulsing sidebar badges for overdue tasks and background daily polling.

### 3.6 Inventory & Product Usage
*   Real-time stock monitoring with low-stock alerts.
*   Direct attachment of products (syringes, implants, etc.) to examinations to track consumption costs.
*   Restocking history and product usage analytics.

### 3.7 Financial Accounting & Analytics
*   Daily, monthly, and yearly revenue reports.
*   Growth charts using Recharts.
*   Detailed breakdown by Treatment Type, Staff Member, and Shift.

### 3.8 Staff Management
*   Staff registration and searchable history.
*   360-degree view of staff interactions including past examinations, payments, and follow-up logs.
*   Remaining balance tracking per staff member.
*   Role-Based Access Control (RBAC): Restricted admin-only routes for accounting and user management.


## 4. Technical Architecture

### 4.1 Tech Stack
*   **Frontend**: React 18, Vite, TypeScript, TailwindCSS, Redux Toolkit.
*   **Backend**: Node.js, Express, TypeScript, Mongoose.
*   **Database**: MongoDB.
*   **Localization**: i18next (English LTR & Arabic RTL support).

### 4.2 Security & Performance
*   **JWT Authentication**: Secure stateless sessions.
*   **RBAC (Role Based Access Control)**: Restricted admin-only routes for accounting and user management.
*   **Offline-First Performance**: Heavy use of database indices and client-side filtering for ultra-fast UI response times.

<!-- 
## 5. Setup & Installation

### Prerequisites
- Node.js 18+
- MongoDB (local or Atlas)

### 1. Installation
```bash
# Backend setup
cd backend
npm install
cp .env.example .env # Update MONGODB_URI and JWT_SECRET

# Frontend setup
cd ../frontend
npm install
```

### 2. Initial Data Seeding
```bash
cd backend
npm run seed
```
*Creates default admin (`admin@dental.com` / `admin123`) and common treatment types.*

### 3. Development Mode
```bash
# Run Backend (Terminal 1)
cd backend
npm run dev

# Run Frontend (Terminal 2)
cd frontend
npm run dev
```
-->
## 5. API Reference (Key Endpoints)

| Module | Endpoint | Method | Role |
| :--- | :--- | :--- | :--- |
| **Recalls** | `/api/recalls` | GET | Auth |
| | `/api/recalls/:id/contact-log` | POST | Auth |
| **Queue** | `/api/queue` | GET | Auth |
| **Patients** | `/api/patients` | POST | Auth |
| **Inventory**| `/api/products` | GET | Auth |
| **Reports** | `/api/accounting/monthly` | GET | Admin |

## 6. Internationalization
The application is fully localized. Toggle between **English (EN)** and **Arabic (AR)** via the globe icon in the sidebar. The UI dynamically adjusts between LTR and RTL layouts.
