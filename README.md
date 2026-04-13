# React Wordle

A simple **React-based web application** published as a **sample deployment project for [Nife.io][1]**.

This repository demonstrates how to run a lightweight React application locally, package it with Docker, and deploy it on [Nife.io][1]. It is intended as a practical sample for validating frontend deployment workflows, container-based delivery, and modern UI applications.[1][2]

---

## Overview

This project is a clone of the popular Wordle game built using React, TypeScript, and Tailwind CSS. It demonstrates modern frontend development practices, state management, and interactive UI design.[3]

If you want a simple frontend project to test deployment on [Nife.io][1], this repository is a good starting point.

---

## Features

| Feature                | Description                            |
| ---------------------- | -------------------------------------- |
| Word guessing game     | Interactive Wordle-style gameplay      |
| Modern UI              | Built with React and Tailwind CSS      |
| Type safety            | Uses TypeScript                        |
| Responsive design      | Works across devices                   |
| Deployment-ready setup | Supports Docker and Nife.io deployment |

---

## Tech Stack

| Technology   | Purpose             |
| ------------ | ------------------- |
| React        | Frontend framework  |
| TypeScript   | Type safety         |
| Tailwind CSS | Styling             |
| Node.js      | Runtime environment |
| Docker       | Container packaging |
| Nife.io      | Deployment platform |

---

## Prerequisites

Before running the project locally, make sure the following are installed.

| Requirement | Notes                        |
| ----------- | ---------------------------- |
| Node.js     | Installed and configured     |
| npm         | Comes with Node.js           |
| Git         | Required to clone repository |

---

## Getting Started

### Clone the repository

```bash
git clone https://github.com/cwackerfuss/react-wordle.git
cd react-wordle
```

### Install dependencies

```bash
npm install
```

### Run the application

```bash
npm run start
```

Then open the application at `http://localhost:3000`.

---

## Run with Docker

This project includes a Dockerfile for container-based execution.

### Build the image

```bash
docker build -t react-wordle .
```

### Run the container

```bash
docker run -p 3000:3000 react-wordle
```

After the container starts, open the app at `http://localhost:3000`.

---

## Deploy on Nife.io

You can deploy this application on [Nife.io][1] using either a Docker image, the source repository, or the CLI.[1][2]

### Option 1: Deploy from a Docker image

First, build and push the image to your preferred container registry.

```bash
docker build -t react-wordle .
docker tag react-wordle <username>/react-wordle:latest
docker push <username>/react-wordle:latest
```

Then configure a new application in Nife.io with the following settings.

| Setting            | Value                                    |
| ------------------ | ---------------------------------------- |
| Source             | Docker Image                             |
| Registry           | Docker Hub or another supported registry |
| Image              | `<username>/react-wordle:latest`         |
| Internal Port      | `3000`                                   |
| External Port      | `80`                                     |
| Suggested Replicas | `1`                                      |

---

### Option 2: Deploy from the Git repository

You can also deploy the project directly from GitHub.

| Setting       | Value                       |
| ------------- | --------------------------- |
| Source        | Git Repository              |
| Provider      | GitHub                      |
| Branch        | `main`                      |
| Internal Port | `3000`                      |
| External Port | `80`                        |
| Build Mode    | Auto-Dockerize with runtime |

---

### Option 3: Deploy with `nifectl`

If you prefer the command line, use the following workflow.

```bash
nifectl auth login
nifectl init
nifectl deploy
```

For step-by-step instructions, see the [Nife.io Quick Deploy documentation][2] and the [nifectl quick start guide][4].

---

## Environment Variables

The following variables are commonly relevant for deployment.

| Variable | Description             | Example      |
| -------- | ----------------------- | ------------ |
| NODE_ENV | Application environment | `production` |

---

## Repository Structure

| Path            | Purpose                      |
| --------------- | ---------------------------- |
| `src/`          | Application source code      |
| `public/`       | Static assets                |
| `Dockerfile`    | Container build instructions |
| `package.json`  | Project dependencies         |
| `tsconfig.json` | TypeScript configuration     |

---

## Troubleshooting

| Issue                       | Suggested fix                 |
| --------------------------- | ----------------------------- |
| Port already in use         | Change port or stop process   |
| Dependencies not installed  | Run `npm install`             |
| App not starting            | Check logs and configuration  |
| Docker build fails          | Verify Dockerfile             |
| Deployment fails on Nife.io | Check ports and configuration |
| App not accessible          | Verify routing and logs       |

---

## Acknowledgements

This repository is maintained by **Nifetency** as a sample deployment project for [Nife.io](https://nife.io).

If this repository is derived from an earlier template or upstream example, it is good practice to retain visible credit to the original author or source repository.
---

## License

This project is licensed under the MIT License.

---

## References

1. [Nife.io](https://nife.io)  
2. [Nife Docs Overview](https://docs.nife.io/overview/)  
3. [Original Repository](https://github.com/wackerfuss/node-multiplayer-snake)  
4. [Nife Quick Start](https://docs.nife.io/Quick-Start)