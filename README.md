# Cyber-Insecurity-Backend

A backend API service built with Node.js, Express, and Prisma ORM, designed to manage authentication, users, assets, transactions, investments, accounts, dashboards, loans, and security logs. This project is structured for modularity and scalability, leveraging modern security and validation practices.

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Features

- RESTful API using Express.js
- User authentication and authorization (JWT based)
- Secure password hashing with bcrypt
- Data validation via Joi and express-validator
- Modular route and controller structure
- Rate limiting and CORS support
- Email integration via Nodemailer
- Database management using Prisma ORM

## Project Structure

> _Note: This structure is based on partial repository analysis. For the full file tree, see the [repository contents](https://github.com/Strange-Leader/Cyber-Insecurity-Backend/tree/master)._

```
/controllers         # Business logic for each resource
/middleware          # Custom Express middleware (auth, validation, etc.)
/prisma              # Prisma schema and migration files
/routes              # Express route definitions (e.g. authRoutes.js)
/services            # Encapsulated service logic (e.g. email, logging)
/utils               # Utility functions
server.js            # Main entry point
Dockerfile           # Containerization setup
package.json         # Project metadata and dependencies
```

## Technologies Used

- **Node.js** (JavaScript runtime)
- **Express.js** (Web framework)
- **Prisma** (ORM for database access)
- **JWT** (Authentication)
- **bcrypt** (Password hashing)
- **Joi & express-validator** (Validation)
- **Nodemailer** (Email services)
- **dotenv** (Environment variable management)
- **CORS** (Security)
- **Docker** (Containerization)

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
   The server will start (default: `http://localhost:5000`).

5. **Database setup:**
   - See `/prisma` for schema and migration commands.

## Available Scripts

- `npm start` — Start server with nodemon (auto-reloads on changes)
- `npm test` — Placeholder for tests (to be implemented)

## API Endpoints

All routes are prefixed with `/api/`:

- `POST   /api/auth`           — Authentication (login/register)
- `GET    /api/users`          — User management
- `GET    /api/assets`         — Asset management
- `GET    /api/transactions`   — Transaction history
- `GET    /api/investments`    — Investments
- `GET    /api/accounts`       — Accounts
- `GET    /api/dashboard`      — Dashboard data
- `GET    /api/loans`          — Loans
- `GET    /api/security-logs`  — Security logs

Error handling is implemented globally and returns JSON errors.

## License

This project is licensed under the ISC License. See `package.json` for details.


---

> **Note**: This README was generated based on an automated analysis of the repository's structure and configuration files. For the most accurate and up-to-date documentation, refer to the source code and comments.
