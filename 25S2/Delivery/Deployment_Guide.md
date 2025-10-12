# Deployment Guide

**Project:** Moral Decisions
**Team:** Moral Decisions
**Version:** 1.0
**Date:** October 13, 2025
**Authors:** Zihao Li

---

## Table of Contents
1. [System Requirements](#1-system-requirements)
2. [Installation Steps](#2-installation-steps)
3. [Running the Application](#3-running-the-application)
4. [Common Issues](#4-common-issues)

---

## 1. System Requirements

### 1.1 Required Software and Versions
- **Node.js:** Version 20.11.x (LTS tested with 20.11.1)
- **npm:** Version 10.x (bundled with Node.js 20)
- **MongoDB:** Version 6.0 or later (Atlas, Replica Set, or standalone instance)
- **Git:** Version 2.40 or later (for cloning the repository)
- **Bash shell:** Any POSIX-compliant shell (required for survey build scripts on macOS/Linux; Windows users can rely on Git Bash or WSL)

### 1.2 Operating System Requirements
- **Supported OS:** Windows 10+, Windows Server 2019+, macOS 12+, Ubuntu 20.04+, Debian 12+
- **Architecture:** x64

### 1.3 Hardware Recommendations
- **CPU:** 2 vCPUs minimum, 4 vCPUs recommended for production use
- **RAM:** 4 GB minimum, 8 GB recommended (especially when running all services on one host)
- **Disk Space:** 10 GB free for code, dependencies, and logs; additional storage as required by MongoDB
- **Network:** Stable outbound connection to the MongoDB host; inbound firewall rules permitting HTTP traffic on the chosen frontend, backend, and survey ports

---

## 2. Installation Steps

### 2.1 Clone Repository

```bash
# Clone the repository
git clone https://github.com/24-S1-2-C-Moral-Decisions/moral-front-end.git
git clone https://github.com/24-S1-2-C-Moral-Decisions/moral-back-end.git
git clone https://github.com/24-S1-2-C-Moral-Decisions/moral-survey.git
# Navigate to project directory
cd moral-decisions
```

Project structure (for reference):
```
moral-decisions/
├── moral-back-end/
├── moral-front-end/
└── moral-survey/
```

### 2.2 Install Dependencies

**Backend Dependencies:**
```bash
# Navigate to backend directory
cd moral-back-end

# Install dependencies
npm install
```

**Frontend Dependencies:**
```bash
# Navigate to frontend directory
cd ../moral-front-end

# Install dependencies
npm install
```

**Survey Dependencies (per sub-project):**
```bash
# Navigate to survey root
cd ../moral-survey/src

# The build script installs packages for each survey
./build.sh   # or bash build.sh on Windows
```

### 2.3 Database Setup

**Step 1: Install MongoDB**
```bash
# Ubuntu example
sudo apt-get update
sudo apt-get install -y mongodb-org

# macOS (Homebrew)
brew tap mongodb/brew
brew install mongodb-community@6.0
```

**Step 2: Create Database**
```bash
# Connect via mongo shell
mongosh "mongodb://<username>:<password>@<host>:27017"

# Inside mongosh
use moral-decisions
db.createCollection("posts")
```

**Step 3: Run Migrations**
```bash
cd moral-back-end
npm run migration:run
```

### 2.4 Environment Configuration

**Backend `.env` file:**
```bash
cd moral-back-end
copy .env.template .env   # Windows
# or
cp .env.template .env     # macOS/Linux
```

Populate `.env` with:
```
# Backend configuration
PORT=3001
DATABASE_URL=mongodb://<user>:<password>@<host>:27017
TFIDF_WORKER_NUM=4
TFIDF_WORKER_BATCH_SIZE=100
DEFAULT_CACHE_TTL=3600
TFIDF_CACHE_TTL=3600
```

**Frontend `.env.local` file:**
```bash
cd ../moral-front-end
```
Create `.env.local` (or `.env.production`):
```
NEXT_PUBLIC_API_URL=https://api.example.com/
NEXT_PUBLIC_SURVEY_URL=https://survey.example.com/
```

**Survey configuration (`config.js`):**
```javascript
production: {
  API_URL: "https://api.example.com/",
  MORAL_URL: "https://app.example.com/",
  SURVEY_PORT: 8080,
  SURVEY_BASE_URL: "https://survey.example.com/"
}
```

---

## 3. Running the Application

### 3.1 Start Backend Server

```bash
cd moral-back-end
npm run build
npm run start:prod
```

**Expected Output:**
```
Nest application successfully started
Listening on port 3001
Connected to MongoDB
```

### 3.2 Start Frontend Application

```bash
cd moral-front-end
npm run build
npm run start
```

**Expected Output:**
```
Ready on http://localhost:3000
Compiled successfully
```

### 3.3 Access the Application

- **Frontend URL:** `http://<host>:3000`
- **Backend API:** `http://<host>:3001`
- **Survey Site:** `http://<host>:8080`
- **API Documentation:** `http://<host>:3001/api` (if Swagger enabled)

### 3.4 Default Ports

- **Frontend:** 3000
- **Backend:** 3001
- **Survey (static site):** 8080
- **MongoDB:** 27017

---

## 4. Common Issues

### 4.1 Application Not Starting

**Problem:**
`npm run start` exits immediately or throws missing module errors.

**Cause:**
Dependencies not installed, build not executed, or incompatible Node.js version.

**Solution:**
```bash
node -v   # should be >= 20
npm install
npm run build
npm run start
```

---

### 4.2 Port Conflicts

**Problem:**
`Error: listen EADDRINUSE` when launching frontend or backend.

**Cause:**
Another process is already using the default port.

**Solution:**
```bash
# Change port in .env or command line
PORT=3100 npm run start:prod

# Windows: find and kill process
netstat -ano | findstr :3001
taskkill /PID <pid> /F

# macOS/Linux:
lsof -i :3001
kill -9 <pid>
```

---

### 4.3 Database Connection Issues

**Problem:**
`MongoServerSelectionError: connect ETIMEDOUT` when running migrations or starting backend.

**Cause:**
Incorrect `DATABASE_URL`, MongoDB service not reachable, firewall blocking port 27017.

**Solution:**
```bash
# Verify MongoDB reachable
mongosh "mongodb://<user>:<password>@<host>:27017/moral-decisions"

# Check service status
systemctl status mongod   # Linux
brew services list        # macOS

# Update .env with correct credentials and host
```

---

### 4.4 Dependency Installation Errors

**Problem:**
`npm install` fails with permission or checksum errors.

**Cause:**
NPM cache corruption, incompatible lockfile, missing Python/build tools on Windows.

**Solution:**
```bash
npm cache clean --force
rimraf node_modules package-lock.json   # Windows (install rimraf globally once)
# or
rm -rf node_modules package-lock.json   # macOS/Linux
npm install
```

---

### 4.5 Environment Variable Issues

**Problem:**
Application cannot reach backend or survey URLs despite servers running.

**Cause:**
Environment files missing or values not matching deployed hostnames.

**Solution:**
```bash
# Backend
type moral-back-end\.env          # Windows
cat moral-back-end/.env           # macOS/Linux

# Frontend
type moral-front-end\.env.local

# Survey config
type moral-survey\config.js

# Restart processes after updating values
```

---

## Quality Checklist
- [x] Clear step-by-step instructions
- [x] All commands provided and tested
- [x] Easy to follow for someone unfamiliar with the project
- [x] Common issues covered
- [x] All sections complete
- [x] Reviewed by team
