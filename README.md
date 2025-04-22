
# TRACE

A full-stack cybersecurity tool built with FastAPI (backend) and SvelteKit (frontend).

## Project Overview

TRACE (Targeted Reconnaissance for Advanced Content Exploitation) is a cybersecurity analysis tool designed to streamline penetration testing for analysts. It integrates multiple tools into a single dashboard, allowing users to scan networks, execute brute-force attacks, detect vulnerabilities, and visualize systems via tree graphs. The system is built for analysts at the Data Analysis Center’s Cyber Experimentation & Analysis Division (DAC CEAD).

## Getting Started

## Prerequisites

Before running TRACE, make sure the following are installed on your system:

- [Python 3.8+](https://www.python.org/downloads/)
- [Node.js (v16 or higher)](https://nodejs.org/)
- [npm (Node Package Manager)](https://www.npmjs.com/)
- [SvelteKit](https://kit.svelte.dev/docs/installation) (installed via `npm install`)
- [Git](https://git-scm.com/)
- [Neo4j Desktop or Server](https://neo4j.com/download/) (for database support)
- [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop) (with WSL2 or Hyper-V enabled)

### Backend (FastAPI)

1. Navigate to the backend folder:
   ```bash
   cd backEnd
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the backend server:
   ```bash
   uvicorn traceMain:app --reload
   ```

> Make sure your Neo4j database is running and properly configured in `config.ini`.

---

### Frontend (SvelteKit)

1. Navigate to the frontend folder:
   ```bash
   cd trace-app
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Install D3.js (for visualizations):
   ```bash
   npm install d3
   ```

4. Run the frontend dev server:
   ```bash
   npm run dev
   ```

> The app will be available at `http://localhost:5173` (or whichever port your SvelteKit dev server chooses).

---

## Running the DVWA Stack with Docker

### 1. Install Docker Desktop

- Download and install [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop)
- Ensure your machine meets the requirements (Windows 10/11, 64-bit, WSL2 or Hyper-V enabled)

### 2. Enable Virtualization

- Make sure virtualization is enabled in:
  - `System Settings > Privacy & Security > Developer Tools`

### 3. Verify Installation

Run the following in PowerShell or terminal:
```bash
docker --version
docker-compose --version
```

### 4. Download and Configure

- Save your `docker-compose.yml` file to a folder, e.g. `C:\Projects\docker-compose-demo`

**Required updates to `docker-compose.yml`:**

```yaml
services:
  apache2:
    platform: linux/arm64

  dvwa:
    platform: linux/amd64

  dvwa-db:
    platform: linux/amd64
    volumes:
      - dvwa-db-data:/var/lib/mysql
      - ./init.sql:/docker-entrypoint-initdb.d/init.sql
```

### 5. File Setup (Required)

- Create `./apache2/` directory and `nginx.conf` file in the same folder as your `.yml`
- Customize the `nginx.conf` file for NGINX

### 6. Launch Docker

```bash
docker pull --platform linux/amd64 vulnerables/web-dvwa
docker-compose up -d
docker ps
```

### 7. Access Services

- DVWA: [http://localhost:8080](http://localhost:8080)
- Apache: [http://localhost:8081](http://localhost:8081)
- NGINX: [http://localhost](http://localhost)

### 8. Manage Docker Services

- Stop the stack:
  ```bash
  docker-compose down
  ```

- View logs:
  ```bash
  docker-compose logs
  docker-compose logs nginx
  ```

---

## License

This project is part of an academic capstone and is not licensed for commercial use. Contact the TRACE team for permissions or inquiries.
