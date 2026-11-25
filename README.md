# 🚀 Employee Management System (EMS)-

---

## 🛠️ Tech Stack & Concepts

| Area | Technology / Pattern | Purpose |
| :--- | :--- | :--- |
| **Frontend** | Angular | User Interface (Forms, Tables, Login, Dashboard) |
| **Backend** | .NET 9 Web API (C#) | RESTful Business Logic APIs |
| **Database** | PostgreSQL / SQL Server | Data storage using Entity Framework Core (EF Core) |
| **Pattern** | Clean Architecture | Code ko layers me divide karna (Clean, Maintainable) |
| **Architecture** | Microservices | Chhoti independent services banana |
| **Tools** | Docker & Docker Compose | Database aur services ko aasani se chalana |

---

## 🧠 Easy Explanations (Samajhne ke liye)

### 1. Clean Architecture Kya Hai?
Clean Architecture me code ko 4 simple layers me baanta jata hai taaki code messy na ho:

```
┌──────────────────────────────────────────────┐
│  1. Domain Layer (Core)                      │
│     Entities / Models (e.g., Employee, User) │
├──────────────────────────────────────────────┤
│  2. Application Layer                        │
│     Interfaces, DTOs, Business Logic         │
├──────────────────────────────────────────────┤
│  3. Infrastructure Layer                     │
│     Database Context (EF Core), Migrations   │
├──────────────────────────────────────────────┤
│  4. API Layer (Web API)                      │
│     Controllers, Endpoints (HTTP Routes)     │
└──────────────────────────────────────────────┘
```

### 2. Microservices Kya Hai?
Sab kuch ek hi bade project (Monolith) me daalne ke bajay, hum 2 simple services banayenge:
1. **Identity / Auth Service:** User Register, Login, JWT Token generation.
2. **Employee Service:** Employee CRUD operations (Add, View, Update, Delete Employee).
3. *(Optional later)* **API Gateway (YARP / Ocelot):** Frontend ke liye single entry point.

---

## 📁 Proposed Folder Structure

```text
EMS/
│
├── README.md                      <-- Guide file
├── docker-compose.yml             <-- Database & Service runners (later)
│
├── backend/                       <-- Backend Microservices (.NET Core)
│   ├── EMS.AuthService/           <-- Authentication Service
│   │   ├── Domain/
│   │   ├── Application/
│   │   ├── Infrastructure/
│   │   └── API/
│   │
│   └── EMS.EmployeeService/       <-- Employee CRUD Service
│       ├── Domain/
│       ├── Application/
│       ├── Infrastructure/
│       └── API/
│
└── frontend/                      <-- Frontend (Angular)
    └── ems-web/                   <-- Angular Application
        ├── src/
        │   ├── app/
        │   │   ├── auth/          <-- Login, Register
        │   │   ├── employees/     <-- Employee List, Add/Edit Form
        │   │   ├── core/          <-- Guards, Interceptors, Services
        │   │   └── shared/        <-- Reusable UI Components
```

---

## 🗺️ Step-by-Step Execution Plan

### 📍 Step 1: Backend Setup (.NET 9 Clean Architecture)
- [ ] Root folder me `backend` directory banana.
- [ ] `EMS.EmployeeService` ke liye Clean Architecture projects create karna:
  - `Domain` (Class Library)
  - `Application` (Class Library)
  - `Infrastructure` (Class Library)
  - `API` (Web API)
- [ ] Projects ke aapas ke references connect karna.

### 📍 Step 2: Database & EF Core Setup
- [ ] `Employee` Entity create karna (Id, FirstName, LastName, Email, Department, Salary, DateOfJoining).
- [ ] PostgreSQL / SQL Server DbContext setup karna.
- [ ] EF Core Migrations create & apply karna.

### 📍 Step 3: CRUD API Endpoints
- [ ] `GET /api/employees` (Sabhi employees fetch karna)
- [ ] `GET /api/employees/{id}` (Single employee details)
- [ ] `POST /api/employees` (Naya employee add karna)
- [ ] `PUT /api/employees/{id}` (Update karna)
- [ ] `DELETE /api/employees/{id}` (Delete karna)
- [ ] Swagger par test karna.

### 📍 Step 4: Frontend Setup (Angular)
- [ ] Angular project create karna (`frontend/ems-web`).
- [ ] Routing & Navigation setup (Navbar, Sidebar).
- [ ] Reusable components aur Auth components integrate karna.
- [ ] Employee List (Table) & Form (Add/Edit) UI design karna.

### 📍 Step 5: Connecting Frontend to Backend
- [ ] Angular `HttpClientModule` setup.
- [ ] Backend me CORS allow karna taaki Angular request accept ho sake.
- [ ] Employee Service ke through data fetch aur display karna.

### 📍 Step 6: Auth Service (Microservice 2)
- [ ] `EMS.AuthService` setup karna.
- [ ] JWT Token generate karna aur Angular me HTTP Interceptor lagana.

---

## ⚡ Useful Commands Cheat Sheet

### .NET CLI:
```bash
# Naya solution file banana:
dotnet new sln -n EMS

# Class library banana:
dotnet new classlib -n ProjectName

# Web API banana:
dotnet new webapi -n ProjectName.API

# Solution me add karna:
dotnet sln add Path/To/Project.csproj

# Run karna:
dotnet run --project Path/To/API.csproj
```

### Angular CLI:
```bash
# Naya Angular project:
ng new ems-web --routing --style=css

# Run dev server:
ng serve -o

# Component generate karna:
ng g c components/employee-list
```

---

*Hamesha step-by-step chaleinge. Jab ek step complete ho jaye, tabhi agle step par move karenge.*
