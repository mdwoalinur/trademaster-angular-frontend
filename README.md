
# TradeMaster Angular Frontend

Angular frontend for the **TradeMaster Inventory and Stock Management System**.

<p>
  <img src="https://img.shields.io/badge/Angular-13-DD0031?style=flat-square&logo=angular&logoColor=white" alt="Angular 13">
  <img src="https://img.shields.io/badge/TypeScript-Frontend-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Bootstrap-UI-7952B3?style=flat-square&logo=bootstrap&logoColor=white" alt="Bootstrap">
  <img src="https://img.shields.io/badge/Backend-Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Deployment-Vercel-000000?style=flat-square&logo=vercel&logoColor=white" alt="Vercel">
  <img src="https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square" alt="Live">
</p>

## Live Application

**TradeMaster is deployed and accessible online.**

**Official IsDB-BISEW Project Showcase:** [View TradeMaster — Inventory & Stock Management System](https://www.isdb-bisew.org/it-scholarship-programme/500/Project-Name---Inventory-%26-Stock-Management-System)

| Service | Platform | Link |
|---|---|---|
| Frontend | Vercel | [Live Application](https://trademaster-angular-frontend.vercel.app/login) |
| Backend REST API | Render | [Backend API](https://trademaster-spring-boot-backend.onrender.com/api) |
| Database | Aiven Cloud | MySQL 8.x |
| Source Code | GitHub | [Frontend Repository](https://github.com/mdwoalinur/trademaster-angular-frontend) |
| Backend Source | GitHub | [Backend Repository](https://github.com/mdwoalinur/trademaster-spring-boot-backend) |
| Project Demo | YouTube | [Watch Demo Video](https://www.youtube.com/watch?v=eN976DJnotM) |

**Live Website:**

https://trademaster-angular-frontend.vercel.app/login

> The backend is hosted on Render. An inactive instance may require additional startup time before responding to requests.

---

## Overview

TradeMaster Angular Frontend is the web client for the TradeMaster Inventory and Stock Management System.

It provides a role-based business management interface for inventory, purchases, sales, payments, finance, reporting, notifications, administration, and operational workflows.

The application communicates with a secured Spring Boot REST API backend.

The project was developed as an academic project under the **IsDB-BISEW IT Scholarship Programme**.

---

## Related Repository

**Spring Boot Backend:**

https://github.com/mdwoalinur/trademaster-spring-boot-backend

---

## Main Features

- Secure login and authenticated application access
- Role-based navigation and permission-aware user interface
- Dashboard with business metrics and summaries
- Product and product variation management
- Category and unit management
- Customer and supplier management
- Warehouse management
- Purchase and purchase return workflows
- Sales and POS workflows
- Sales return workflows
- Inventory overview and stock tracking
- Stock adjustments and warehouse transfers
- Low-stock monitoring
- Payment management
- Payment approval workflow
- Financial account management
- Payment reconciliation
- Expense and wastage management
- Sales, purchase, inventory, financial, and tax reports
- Notifications
- User and role administration
- System settings
- Audit log viewing
- Global search
- Barcode scanning support
- English and Bangla runtime translation
- Theme support
- Responsive business dashboard

---

## Technology Stack

### Frontend

- Angular 13
- TypeScript
- JavaScript
- HTML5
- CSS3
- Bootstrap
- RxJS
- Angular Router
- Angular HTTP Client
- JWT Authentication
- REST API Integration

### Backend

- Java 17
- Spring Boot 4.0.3
- Spring Security
- Spring Data JPA
- Hibernate
- JWT Authentication
- Maven

### Database

- MySQL 8.x
- Aiven Cloud MySQL

### Deployment

- Vercel — Angular Frontend
- Render — Spring Boot Backend
- Aiven — Cloud MySQL Database
- GitHub — Source Code and Version Control

---

## Application Architecture

TradeMaster follows a separated frontend and backend architecture.

```text
                  User / Browser
                         |
                         v
                 Angular 13 Frontend
                    (Vercel)
                         |
                  HTTPS / REST API
                         |
                         v
                Spring Boot Backend
                     (Render)
                         |
                 Spring Security
                 Controllers / DTOs
                 Services / JPA
                         |
                         v
                  MySQL Database
                   (Aiven Cloud)
```

The Angular application sends HTTP requests to the Spring Boot backend. The backend handles authentication, authorization, business logic, and database operations.

---

## Requirements

- Node.js compatible with Angular CLI 13
- npm
- Git
- Angular CLI 13
- TradeMaster Spring Boot backend running on port `8080` for local development

**Backend Repository:**

https://github.com/mdwoalinur/trademaster-spring-boot-backend

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/mdwoalinur/trademaster-angular-frontend.git
```

### 2. Navigate to the Project Directory

```bash
cd trademaster-angular-frontend
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure the Backend API

For local development, open:

`src/environments/environment.ts`

Use the local Spring Boot backend API URL:

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080/api'
};
```

Make sure the Spring Boot backend is running and connected to the MySQL database.

### 5. Start the Angular Application

```bash
npm start
```

Open:

http://localhost:4200

---

## Environment Configuration

The application uses separate environment configurations for development and production.

### Development Environment

File:

`src/environments/environment.ts`

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080/api'
};
```

### Production Environment

File:

`src/environments/environment.prod.ts`

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://trademaster-spring-boot-backend.onrender.com/api'
};
```

The Angular production build uses the production environment configuration.

No database credentials or JWT signing secrets are required in the Angular environment files.

---

## Backend REST API Integration

The Angular frontend communicates with the Spring Boot backend through REST APIs.

### Local Backend API

```text
http://localhost:8080/api
```

### Production Backend API

```text
https://trademaster-spring-boot-backend.onrender.com/api
```

### Authentication Endpoint

```http
POST /api/auth/login
```

The backend validates login credentials and handles JWT-based authentication.

### Request Flow

```text
Angular Component
       |
       v
Angular Service
       |
       v
Angular HttpClient
       |
       v
Spring Boot REST API
       |
       v
Service Layer
       |
       v
Repository / Hibernate
       |
       v
MySQL Database
```

---

## Authentication and Authorization

TradeMaster uses JWT-based authentication with Spring Security.

The frontend provides:

- Login interface
- Authenticated navigation
- Role-based UI access
- HTTP communication with secured APIs
- Authentication-based application routing

The backend is responsible for enforcing security and access permissions.

### CORS Configuration

The deployed Spring Boot backend permits requests from these frontend origins:

```text
https://trademaster-angular-frontend.vercel.app
http://localhost:4200
```

This supports both production access and local Angular development.

### Demo Login

The application requires a valid user account.

For security reasons, production administrator passwords and JWT secrets are not published in this repository.

Authorized reviewers may request demo account credentials separately.

---

## Production Build

Generate an Angular production build using:

```bash
npm run build
```

The production output directory is:

```text
dist/trademaster-ng
```

The generated build files are used for frontend deployment.

---

## Deployment

### Angular Frontend — Vercel

The frontend is deployed on Vercel and connected to the `main` branch of this GitHub repository.

**Production Website:**

https://trademaster-angular-frontend.vercel.app

### Vercel Build Configuration

| Setting | Value |
|---|---|
| Framework Preset | Other |
| Build Command | `npm run build` |
| Output Directory | `dist/trademaster-ng` |
| Install Command | `npm install` |
| Root Directory | `./` |
| Production Branch | `main` |

### Spring Boot Backend — Render

The backend REST API is deployed on Render.

**Production Backend URL:**

https://trademaster-spring-boot-backend.onrender.com

**API Base URL:**

https://trademaster-spring-boot-backend.onrender.com/api

The backend connects to the Aiven MySQL cloud database.

### MySQL Database — Aiven

Database service: Aiven Cloud MySQL

Database name:

```text
trademaster
```

The backend manages database connectivity using secure configuration and environment variables.

Database credentials must never be included in frontend source code or public documentation.

---

## Testing and Verification

The following production checks have been completed:

- Angular production build successful
- Vercel frontend deployment successful
- Render backend deployment successful
- Aiven MySQL backend connectivity successful
- Frontend-to-backend authentication successful
- Administrator login successful
- Administrator dashboard opened successfully

Full functional regression testing across every business module is separate from these deployment checks.

---

## Project Demonstration

### YouTube Demo Video

The project was demonstrated as part of the IsDB-BISEW IT Scholarship Programme.

**Watch the Project Demo:**

https://www.youtube.com/watch?v=eN976DJnotM

### Official IsDB-BISEW Project Showcase

TradeMaster — Inventory & Stock Management System is featured on the official IsDB-BISEW website.

**Project Showcase:**

[View TradeMaster on IsDB-BISEW](https://www.isdb-bisew.org/it-scholarship-programme/500/Project-Name---Inventory-%26-Stock-Management-System)

---

## Project Information

| Field | Details |
|---|---|
| Project Name | TradeMaster |
| Project Type | Inventory & Stock Management System |
| Frontend | Angular 13 |
| Backend | Java 17, Spring Boot 4.0.3 |
| Database | MySQL 8.x |
| Frontend Hosting | Vercel |
| Backend Hosting | Render |
| Database Hosting | Aiven Cloud |
| Training Programme | IsDB-BISEW IT Scholarship Programme |
| Developer | Md. Woalinur |

---

## Author

**MD. WOALINUR**

Full-Stack Web & Software Developer

**GitHub:** https://github.com/mdwoalinur

**Email:** mdwoalinur@gmail.com

---

## Repository Links

**Frontend GitHub:**

https://github.com/mdwoalinur/trademaster-angular-frontend

**Backend GitHub:**

https://github.com/mdwoalinur/trademaster-spring-boot-backend

**Live Frontend:**

https://trademaster-angular-frontend.vercel.app/login

**Live Backend API:**

https://trademaster-spring-boot-backend.onrender.com/api

**Official Project Showcase:**

https://www.isdb-bisew.org/it-scholarship-programme/500/Project-Name---Inventory-%26-Stock-Management-System

---

## Project Status

**Live — Deployed on Vercel, Render, and Aiven Cloud.**

The TradeMaster Angular frontend is accessible online. Production administrator login and dashboard navigation have been verified successfully.
