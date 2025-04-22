
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

## License

This project is part of an academic capstone and is not licensed for commercial use. Contact the TRACE team for permissions or inquiries.
