# TRACE

A full-stack cybersecurity tool built with FastAPI (backend) and SvelteKit (frontend).

## Project Overview

**TRACE** (Targeted Reconnaissance for Advanced Content Exploitation) is a cybersecurity analysis tool designed to streamline penetration testing for analysts. It integrates multiple tools into a single dashboard, allowing users to scan networks, execute brute-force attacks, detect vulnerabilities, and visualize systems via tree graphs. The system is built for analysts at the Data Analysis Center’s Cyber Experimentation & Analysis Division (DAC CEAD).

---

## 🚀 Quick Start

To install and run TRACE with **all components automatically**, use the provided script:

```bash
bash installer.sh
```

> This installs and launches the backend, frontend, and Docker services in one step.  
> **Use the manual steps below only if you prefer to set things up yourself.**

---

## Manual Setup (Optional)

### Prerequisites

Ensure the following are installed:

- [Python 3.8+](https://www.python.org/downloads/)
- [Node.js (v16 or higher)](https://nodejs.org/)
- [npm](https://www.npmjs.com/)
- [SvelteKit](https://kit.svelte.dev/docs/installation)
- [Git](https://git-scm.com/)
- [Neo4j Desktop or Server](https://neo4j.com/download/)
- [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop) (WSL2 or Hyper-V enabled)

---

### Backend (FastAPI)

```bash
cd backEnd
pip install -r requirements.txt
uvicorn traceMain:app --reload
```

> Ensure your Neo4j database is running and correctly configured in `config/config.ini`.

---

### Frontend (SvelteKit)

```bash
cd trace-app
npm install
npm install d3
npm run dev
```

> The app will be available at `http://localhost:5173`.

---

### DVWA Stack with Docker (Optional)

1. **Install Docker Desktop**  
   Ensure WSL2 or Hyper-V is enabled (Windows).

2. **Enable Virtualization**  
   In your BIOS or through:  
   `System Settings > Privacy & Security > Developer Tools`

3. **Verify Docker Installation**

```bash
docker --version
docker-compose --version
```

4. **Prepare Required Files**

- Create a `./apache2/` directory and an `nginx.conf` file in the same folder as your `docker-compose.yml`
- Customize `nginx.conf` for your NGINX setup

5. **Launch Docker Stack**

```bash
docker-compose up -d
docker ps
```

6. **Access Services**

- DVWA: [http://localhost:8080](http://localhost:8080)  
- Apache: [http://localhost:8081](http://localhost:8081)  
- NGINX: [http://localhost](http://localhost)

7. **Manage Docker Services**

```bash
docker-compose down
docker-compose logs
docker-compose logs nginx
```

---

## License

This project is part of an academic capstone and is not licensed for commercial use.  
Contact the TRACE team for permissions or inquiries.
