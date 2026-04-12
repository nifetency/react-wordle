# React Wordle

## Overview

A clone of the popular Wordle game built using:

- React
- TypeScript
- Tailwind CSS

This project demonstrates:
- Modern frontend development
- State management in React
- Interactive UI design

Originally based on:
https://github.com/cwackerfuss/react-wordle

---

## Requirements

Make sure you have the following installed:

- Node.js
- npm
- Git

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/cwackerfuss/react-wordle.git
cd react-wordle
```

---

### 2. Install Dependencies

```bash
npm install
```

---

### 3. Run the Application

```bash
npm run start
```

---

### 4. Open in Browser

Visit:

```
http://localhost:3000
```

---

## Run with Docker (Optional)

### Development

```bash
docker build -t react-wordle:dev .
docker run -d -p 3000:3000 react-wordle:dev
```

---

### Production

```bash
docker build --target=prod -t react-wordle:prod .
docker run -d -p 80:80 react-wordle:prod
```

---

## Features

- Word guessing gameplay
- Interactive UI
- Responsive design
- Multiple language support (customizable)

---

## Deployment on NIFE

Deploy your application using the NIFE platform:

https://launch.nife.io/

Deployment flow:

```text
Source → Build → Resources → Review → Deploy
```

Prerequisite: Ensure a workload (Deployment, CronJob, or StatefulSet) exists.

---

## Method 1: Deploy via Docker Image

### Step 1: Build and Push Image

```bash
docker build -t react-wordle .
docker tag react-wordle <username>/react-wordle:latest
docker push <username>/react-wordle:latest
```

---

### Step 2: Configure Source

- Source: Docker Image
- Registry: Docker Hub
- Image: `<username>/react-wordle:latest`
- Tag: `latest`

---

### Step 3: Build Configuration

- Internal Port: `3000`
- External Port: `80`

Optional environment variables:

| Key      | Value      |
|----------|------------|
| NODE_ENV | production |

---

### Step 4: Resources Configuration

- Region: e.g., `ap-south-1`
- Resource Type: CPU

Recommended settings:

- CPU Request: `250m`
- Memory Request: `512MB`
- CPU Limit: `500m`
- Memory Limit: `1GB`

---

### Step 5: Deploy

- Strategy: Rolling
- Workload: Deployment
- Routing Policy: Latency
- Replicas: 1–2

Click **Deploy**.

---

## Method 2: Deploy via Git Repository

### Step 1: Select Source

- Source: Git Repository
- Provider: GitHub
- Branch: `main`

---

### Step 2: Build Configuration

- Internal Port: `3000`
- External Port: `80`

Enable:

```
Auto-Dockerize with Runtime
```

---

### Step 3: Build and Security

NIFE automatically performs:

- SAST
- SCA
- Container scan
- IaC scan

Resolve any critical issues before proceeding.

---

### Step 4: Resources and Deploy

Use the recommended configuration above and deploy.

---

## Deployment using nifectl (CLI)

### Step 1: Download nifectl

https://docs.nife.io/Quick-Start/Nifectl

---

### Step 2: Open Terminal

- Type `cmd` in the address bar  
  OR  
- Right-click → **Open in Terminal**

---

### Step 3: Verify Installation

```bash
nifectl --help
```

---

## Deployment Steps

### Step 1: Login

```bash
nifectl auth login
```

---

### Step 2: Initialize Project

```bash
nifectl init
```

Provide:
- Application name
- Organization
- Repository URL
- Branch (`main`)

---

### Step 3: Configure Deployment

- Deployment Type: Deployment
- Resource Type: CPU
- Replicas: 1

Ports:
- Internal: `3000`
- External: `80`

---

### Step 4: Deploy

```bash
nifectl deploy
```

---

### Step 5: Select Region

Example:

```
IND - Mumbai
```

---

### Step 6: Monitor Deployment

Monitor logs for:
- Validation
- Build
- Deployment

---

### Step 7: Access Application

```
https://<your-nife-url>
```

---

## Dependencies

| Dependency  | Purpose                |
|-------------|------------------------|
| React       | Frontend framework     |
| TypeScript  | Type safety            |
| Tailwind CSS| Styling                |
| Node.js     | Runtime environment    |

---

## Environment Variables

| Variable | Description             | Default     |
|----------|-------------------------|-------------|
| NODE_ENV | Application environment | development |

---

## Troubleshooting

| Issue                   | Solution                                  |
|------------------------|--------------------------------------------|
| Port already in use    | Change port or stop running process        |
| Node not installed     | Install Node.js (`node -v`)                |
| Dependencies missing   | Run `npm install`                          |
| App not starting       | Check logs and configuration               |
| Docker build fails     | Verify Dockerfile                          |
| Deployment fails       | Check logs and environment variables       |
| App not accessible     | Verify port mapping and routing            |

---

## Acknowledgements

This repository is maintained by Nifetency as a sample deployment project for Nife.io.

If derived from an upstream example, proper credit should be given to the original author.

---

## License

This project is licensed under the MIT License.

---

## References

- Original Repository: https://github.com/cwackerfuss/react-wordle
- NIFE Platform: https://nife.io/