# PlusePoint

# PulsePoint Smart Healthcare + PharmaGuard

A full-stack digital hospital platform with symptom guidance, health records, emergency support, and a precision medicine module (PharmaGuard) for pharmacogenomic drug risk analysis.

## Project Name
`PulsePoint Smart Healthcare + PharmaGuard`

## Live Deployment Links
- Main Web App (Frontend): `https://gururajachar2008.github.io/PlusePoint_front-end_deployment/`
- GitHub Repository: `https://github.com/GururajAchar2008/PlusePoint.git`
- LinkedIn Demo Video: `https://www.linkedin.com/posts/YOUR-VIDEO-POST-LINK`


## Core Modules
1. Patient Experience
- Home dashboard
- Symptom checker
- Health record
- Emergency support

2. Precision Medicine (PharmaGuard)
- Upload `.vcf` (up to 5 MB)
- Enter one or multiple drugs
- Parse variants for key pharmacogenes
- Rule-based risk assessment
- Clinical recommendation output
- JSON report copy/download

## Tech Stack
### Frontend
- React + Vite
- Tailwind CSS
- Lucide React icons

### Backend
- Python Flask
- Flask-MySQLdb
- MySQL Aiven cloud

### Database
- MySQL tables for departments, symptoms, patients, testimonials, and pharmacogenomic reports

## Repository Structure
```text
Helth-Teck/
├── Front-end/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── App.jsx
│   └── ...
├── Backend/
│   ├── app.py
│   ├── sample_vcfs/
│   └── ...
└── README.md
```

## High-Level Architecture
1. Frontend captures user input (forms and VCF upload).
2. Backend API validates input and applies domain logic.
3. MySQL stores reference and transactional data.
4. API returns structured JSON responses.
5. Frontend renders visual dashboards and reports.

## Precision Medicine Flow
1. User uploads a VCF file.
2. User enters drug names (comma-separated).
3. Backend parses VCF and extracts supported gene variants.
4. Backend computes diplotype/phenotype and risk label per drug.
5. Backend returns report JSON with recommendation and explainable section.
6. Frontend shows cards + details and allows JSON copy/download.

## Local Setup (Full Stack)
### 1) Backend
```bash
cd Backend
pip install -r requirements.txt
python3 app.py
```
Backend runs on `http://localhost:5000` by default.

### 2) Frontend
```bash
cd Front-end
npm install
npm run dev
```
Frontend runs on `http://localhost:3000` by default.

## Environment Variables
Copy one of these templates:
- `.env.example` (root)
- `Backend/.env.example`
- `Front-end/.env.example`

### Frontend
- `VITE_API_BASE_URL` (example: `https://plusepoint-backend-deployment.onrender.com`)

### Backend
- `MYSQL_HOST`
- `MYSQL_PORT`
- `MYSQL_USER`
- `MYSQL_PASSWORD`
- `MYSQL_DB`
- `MYSQL_SSL_MODE` (optional)
- `MYSQL_SSL_CA` (optional)
- `PHARMAGUARD_USE_LLM` (optional)
- `OPENAI_API_KEY` (optional)
- `PHARMAGUARD_LLM_MODEL` (optional, default: `openrouter/aurora-alpha`)
- `OPENAI_API_URL` (optional, default: `https://openrouter.ai/api/v1/chat/completions`)
- `OPENROUTER_SITE_URL` (optional)
- `OPENROUTER_APP_NAME` (optional)

## API Overview
- `GET /` Health check
- `GET /api/reference-data`
- `POST /api/patients`
- `GET /api/patients/latest`
- `GET /api/pharmacogenomics/meta`
- `POST /api/pharmacogenomics/analyze`

## Usage Examples
### Health Record
1. Open `Health Record` from sidebar.
2. Enter patient details (name, blood group, allergies, chronic conditions).
3. Click `Save Record` to persist in MySQL.

### Symptom Checker
1. Open `Symptom Checker`.
2. Select a symptom and click `Check`.
3. Review recommended department and urgency.

### Precision Medicine
1. Open `Precision Medicine`.
2. Upload a `.vcf` file and enter one or more drugs.
3. Click analyze to view risk cards and JSON output.

## Demo Test Assets
Sample VCF files for precision medicine testing:
- `Backend/sample_vcfs/patient_demo_001.vcf`
- `Backend/sample_vcfs/patient_demo_002.vcf`

## Deployment Notes
### Frontend (Vercel/Netlify)
- Build command: `npm run build`
- Output directory: `dist`
- Set `VITE_API_BASE_URL` to deployed backend URL

### Backend (Render/Railway)
- Start command: `python app.py`
- Configure MySQL env vars
- Prefer managed MySQL (Aiven)

## Team
- Gururaj achar : Developer (Team lead)
- Harshith R Naik : Presentater
- Goutham E : Designer

## License
For hackathon/demo use.
