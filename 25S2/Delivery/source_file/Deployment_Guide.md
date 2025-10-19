# Deployment Guide

## Table of Contents
1. [System Requirements](#1-system-requirements)  
2. [Installation Steps](#2-installation-steps)  
3. [Running the Application](#3-running-the-application)  
4. [Common Issues](#4-common-issues)

---

## 1. System Requirements

### 1.1 Required Software and Versions
- **Node.js:** Version 20.11.x (tested with 20.11.1)
- **npm:** Version 10.x (bundled with Node.js 20)
- **MongoDB:** Version 6.0 or later (Atlas, replica set, or standalone)
- **Git:** Version 2.40 or later
- **Bash shell:** Any POSIX-compliant shell (for `build.sh` and `publish.sh`; Windows users can use Git Bash or WSL)

### 1.2 Operating System Requirements
- **Supported OS:** Windows 10+, Windows Server 2019+, macOS 12+, Ubuntu 20.04+, Debian 12+
- **Architecture:** x64

### 1.3 Hardware Recommendations
- **CPU:** Minimum 2 vCPUs (4 recommended for production)
- **RAM:** Minimum 4 GB (8 GB recommended when all services run on one host)
- **Disk Space:** 10 GB free for code, dependencies, and logs (plus MongoDB storage)
- **Network:** Stable outbound access to MongoDB; inbound firewall rules allowing ports 3000, 3001, and 8080

---

## 2. Installation Steps

### 2.1 Clone Repositories
```bash
git clone https://github.com/24-S1-2-C-Moral-Decisions/moral-back-end.git
git clone https://github.com/24-S1-2-C-Moral-Decisions/moral-front-end.git
git clone https://github.com/24-S1-2-C-Moral-Decisions/moral-survey.git
```

Set a deployment root for convenience (update the path as needed):
```bash
export DEPLOY_ROOT=/path/to/moral-decisions
mkdir -p "$DEPLOY_ROOT"
mv moral-back-end moral-front-end moral-survey "$DEPLOY_ROOT"/
```

Project structure:
```
$DEPLOY_ROOT/
├── moral-back-end/
├── moral-front-end/
└── moral-survey/
```

### 2.2 Backend (`moral-back-end`)
- **Install dependencies**
  ```bash
  cd "$DEPLOY_ROOT/moral-back-end"
  npm install
  ```
- **Configure environment variables**  
  Create `moral-back-end/.env/.env.production`:
  ```bash
  cat > "$DEPLOY_ROOT/moral-back-end/.env/.env.production" <<'EOF'
  PORT=3001
  DATABASE_URL=mongodb://<your-mongo-host>:27017
  TFIDF_WORKER_NUM=4
  TFIDF_WORKER_BATCH_SIZE=500
  DEFAULT_CACHE_TTL=3600
  NODE_ENV=production
  EOF
  ```
  Replace `<your-mongo-host>` with the actual MongoDB connection string.
- **Build**
  ```bash
  npm run build
  ```

### 2.3 Frontend (`moral-front-end`)
- **Install dependencies**
  ```bash
  cd "$DEPLOY_ROOT/moral-front-end"
  npm install
  ```
- **Configure environment variables**  
  Create `moral-front-end/.env.local`:
  ```bash
  cat > "$DEPLOY_ROOT/moral-front-end/.env.local" <<'EOF'
  NEXT_PUBLIC_API_URL="http://115.146.86.210:3001/"
  NEXT_PUBLIC_SURVEY_URL="http://115.146.86.210:8080/"
  EOF
  ```
- **Build**
  ```bash
  npm run build
  ```

### 2.4 Survey (`moral-survey`)
- **Prepare scripts (first run)**
  ```bash
  cd "$DEPLOY_ROOT/moral-survey/src"
  chmod +x build.sh publish.sh
  ```
- **Build static files**
  ```bash
  ./build.sh
  ./publish.sh
  ```
  Output is placed in `$DEPLOY_ROOT/moral-survey/src/build`.

---

## 3. Running the Application

### 3.1 Start Backend
```bash
cd "$DEPLOY_ROOT/moral-back-end"
NODE_ENV=production PORT=3001 npm run start:prod
```
Expected console output includes:
```
Nest application successfully started
Listening on port 3001
Connected to MongoDB
```

### 3.2 Start Frontend
```bash
cd "$DEPLOY_ROOT/moral-front-end"
HOST=0.0.0.0 PORT=3000 npm run start
```
Expected output:
```
Ready on http://0.0.0.0:3000
Compiled successfully
```

### 3.3 Serve Survey
```bash
cd "$DEPLOY_ROOT/moral-survey/src/build"
npx serve -l tcp://0.0.0.0:8080 .
```
Keep the terminal session running (or manage the process with `pm2`, `systemd`, etc.).

### 3.4 Access Points
- Frontend: `http://115.146.86.210:3000/`
- Backend API: `http://115.146.86.210:3001/`
- Survey site: `http://115.146.86.210:8080/`
- API health check (example): `http://115.146.86.210:3001/health`

---

## 4. Common Issues

### 4.1 Application Not Starting
- **Symptom:** `npm run start` exits immediately or reports missing modules.  
- **Fix:** Verify Node.js version (`node -v`), run `npm install`, then rebuild (`npm run build`) before restarting.

### 4.2 Port Conflicts
- **Symptom:** `Error: listen EADDRINUSE` on ports 3000, 3001, or 8080.  
- **Fix:** Identify conflicting processes (`sudo lsof -i :3001`) and stop them, or override ports when starting (`PORT=3100 npm run start:prod`).

### 4.3 Database Connection Issues
- **Symptom:** `MongoServerSelectionError` when starting the backend.  
- **Fix:** Confirm the MongoDB host is reachable using `mongosh`, check firewall rules, and ensure the `DATABASE_URL` in `.env.production` is correct.

### 4.4 Dependency Installation Errors
- **Symptom:** `npm install` fails with permission or checksum errors.  
- **Fix:** Clear the npm cache (`npm cache clean --force`), delete `node_modules` and lockfiles, then reinstall.

### 4.5 Environment Variable Issues
- **Symptom:** Frontend cannot reach backend or survey.  
- **Fix:** Review `.env/.env.production`, `.env.local`, and survey config; restart each service after changes.

### 4.6 Survey Build Problems
- **Symptom:** `build.sh` or `publish.sh` fails.  
- **Fix:** Ensure Node.js 20 is installed, rerun `npm install` within each `moral-survey/src/moral-survey-*` folder if the script reports missing packages.

---

**Quality Checklist**
- [x] Clear step-by-step instructions  
- [x] All commands provided and tested  
- [x] Easy to follow for new deployers  
- [x] Common issues covered  
- [x] All sections complete  
- [x] Reviewed by team  
