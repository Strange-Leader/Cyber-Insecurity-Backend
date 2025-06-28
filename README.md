# Cyber-Insecurity-Backend

A robust backend API service for managing users, assets, transactions, investments, accounts, dashboards, loans, and security logs. Built for extensibility, modularity, and strong security, this project leverages modern Node.js practices and incorporates several custom-crafted features.

---

## Table of Contents

- [Features](#features)
- [Unique & Custom Implementations](#unique--custom-implementations)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [API Endpoints](#api-endpoints)
- [License](#license)

---

## Features

- RESTful API using Express.js
- User authentication and authorization (JWT-based)
- Multi-factor authentication (OTP via email)
- Secure password hashing (bcrypt, 12 salt rounds)
- Comprehensive security event logging
- Data validation via Joi and express-validator
- Modular, role-based access control via middleware
- Rate limiting and CORS support
- Email integration via Nodemailer
- Prisma ORM for database management (PostgreSQL recommended)
- Dockerized for easy deployment

---

## Unique & Custom Implementations

- **Centralized Security Event Logging**:  
  A custom-built logger (`utils/securityLogger.js`) records granular security-related events (auth, asset, account, transaction, loan, and suspicious activity) directly to the database with associated user, event context, IP, and user-agent. This enables advanced auditing and anomaly detection.

- **Custom Account Number Generation**:  
  Implements a self-developed function to generate unique account numbers with a fixed prefix and a 16-digit random component.

- **Granular Role-Based Access Control**:  
  Middleware restricts sensitive asset and admin endpoints, ensuring only verified or admin users can access critical operations.

- **Integrated OTP Workflow**:  
  OTP handling for account verification and login, including expiry checks, hashed OTP comparison, and security event logging for both success and failure.

- **Rich Dashboard Aggregation**:  
  Back-end aggregation of financial data (net transactions, total assets, total investments) for efficient dashboard rendering, not just simple CRUD.

- **Security-Embedded Loan Processing**:  
  All critical loan actions (application, approval, rejection) log detailed security events with context (amount, account, initiator/admin, reasons, etc.) for transparency and traceability.

---

## Project Structure

```
/controllers         # Business logic for each resource (auth, asset, dashboard, loan, transaction, etc.)
/middleware          # Express middleware (auth, validation, role, etc.)
/prisma              # Prisma schema and migration files
/routes              # Route definitions
/services            # Service logic (email, logging, etc.)
/utils               # Utility functions (auth, securityLogger, accountUtils, etc.)
server.js            # Main entry point
Dockerfile           # Containerization
package.json         # Dependency management
```

---

## Technologies Used

- **Node.js** (JavaScript runtime)
- **Express.js** (Web framework)
- **Prisma** (ORM)
- **JWT** (Authentication)
- **bcrypt** (Password hashing)
- **Joi** & **express-validator** (Validation)
- **Nodemailer** (Email)
- **dotenv** (Env vars)
- **CORS** (Security)
- **Docker** (Containerization)

---

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Strange-Leader/Cyber-Insecurity-Backend.git
   cd Cyber-Insecurity-Backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**
   - Copy `.env.example` to `.env` and fill in required settings.

4. **Run the development server:**
   ```bash
   npm start
   ```
   The server starts at `http://localhost:5000` by default.

5. **Database setup:**
   - See `/prisma` for schema and migration commands.

---

## Available Scripts

- `npm start` — Start server with nodemon (auto-reloads)
- `npm test` — Placeholder for tests

---

## API Endpoints

All routes are prefixed with `/api/`:

- `POST   /api/auth`           — Authentication (login/register/OTP)
- `GET    /api/users`          — User management
- `GET    /api/assets`         — Asset management (admin required for some routes)
- `GET    /api/transactions`   — Transaction history
- `GET    /api/investments`    — Investments
- `GET    /api/accounts`       — Accounts
- `GET    /api/dashboard`      — Dashboard aggregation
- `GET    /api/loans`          — Loans
- `GET    /api/security-logs`  — Security logs (admin only)

Global error handling returns JSON errors.

---

## License

ISC License (see `package.json`).

---

> This README is based on code analysis. For the latest details, see the source and comments.
