
# TRACE

A full-stack cybersecurity tool built with FastAPI (backend) and SvelteKit (frontend).

## Project Overview

TRACE (Targeted Reconnaissance for Advanced Content Exploitation) is a cybersecurity analysis tool designed to streamline penetration testing for analysts. It integrates multiple tools into a single dashboard, allowing users to scan networks, execute brute-force attacks, detect vulnerabilities, and visualize systems via tree graphs. The system is built for analysts at the Data Analysis Center’s Cyber Experimentation & Analysis Division (DAC CEAD).

## Getting Started

### Backend (FastAPI)

1. Navigate to the backend folder:
   ```bash
   cd backend
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
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the frontend dev server:
   ```bash
   npm run dev
   ```

> The app will be available at `http://localhost:5173` (or whichever port your SvelteKit dev server chooses).

---

## 🛠️ Key Features

- Project creation, import, export, lock/unlock
- Web crawling and directory brute-forcing
- HTTP request management and proxy routing
- SQL Injection detection and database enumeration
- AI-powered username/password generation
- Real-time progress tracking and visualizations (tree graph)
- Exporting results in various formats (CSV/XML)

---

## Tech Stack

- **Frontend**: SvelteKit v2.16.1 (compatible with Svelte v5.19.2)
- **Backend**: Python 3.14 (FastAPI)
- **Database**: Neo4j 5.26.1
- **UI Library**: shadcn-svelte 0.14.0

---

## Minimum System Requirements

- 4-core 2.5GHz processor
- 8GB RAM
- 10GB free storage
- Neo4j running locally

---

## License

This project is part of an academic capstone and is not licensed for commercial use. Contact the TRACE team for permissions or inquiries.
