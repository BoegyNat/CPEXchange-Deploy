# CPExchange - Deployment Guide

This repository contains the deployment configuration for the **CPExchange** platform using Docker Compose.

## 🧰 Prerequisites

Make sure you have the following installed:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## ⚙️ Setup Instructions

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/CPExchange-Deploy.git
   cd CPExchange-Deploy
   ```

2. **Rename the environment file**
   Before running the project, rename .env.example to .env, and fill in all required environment variables.

   ```bash
   cp .env.example .env
   ```

   Update the values in .env according to your setup (e.g., database credentials, JWT secret, URLs, etc.).

3. **Run the project using Docker Compose**

   ```bash
   docker-compose up -d
   ```

   This command will spin up the following services:

   - backend - Node.js + Express.js API
   - frontend - React.js application
   - db - MySQL 8.0 database

4. **Access the application**

   - Frontend: http://localhost:3002

   - Backend API: http://localhost:5002

## 🗃️ Docker Services Overview

| Service  | Host Port → Container Port | Description                |
| -------- | -------------------------- | -------------------------- |
| frontend | 3002 → 3000                | React-based user interface |
| backend  | 5002 → 5002                | Node.js API service        |
| db       | 3307 → 3306                | MySQL 8.0 database         |

## 📁 Volumes

- db_data: Persists MySQL data.
- file: Persists user-uploaded files from the backend.

## 🔄 Stopping the Services

To stop the running containers:

```bash
docker-compose down
```

## 🧼 Clean Up (Optional)

If you want to remove all containers, networks, and volumes:

```bash
docker-compose down -v
```
