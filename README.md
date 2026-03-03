Smart Public Service CRM (PS-CRM)

An AI-powered centralized digital command center for managing citizen grievances with automated workflows, real-time tracking, and transparent resolution monitoring.

Overview

Smart Public Service CRM (PS-CRM) is a governance platform designed to:

Centralize and organize citizen complaints

Automate task assignment workflows

Track grievance resolution in real time

Enforce SLA-based escalation rules

Provide transparency to citizens and administrators

Deliver AI-driven insights for policy-level decision making

The system transforms traditional complaint portals into an intelligent civic workflow engine.

Key Features
AI-Powered Intelligence

NLP-based complaint categorization

Automatic priority scoring

Duplicate complaint detection

Sentiment analysis

Smart department routing

Workflow Automation

Role-based task assignment

SLA tracking and breach alerts

Automated escalation engine

Real-time status updates

Audit logging

Governance Analytics

Heatmaps for complaint clusters

Department performance metrics

Resolution time analysis

Predictive backlog forecasting

Citizen-Centric Interface

Real-time complaint tracking

Multilingual support

Geo-tagged submissions

Media uploads (images and videos)

Mobile-responsive interface

System Architecture
Citizen Portal
      ↓
API Gateway
      ↓
Complaint Service
      ↓
Workflow Engine
      ↓
AI Classification Service
      ↓
Assignment Engine
      ↓
Notification System
      ↓
Analytics Dashboard
Tech Stack
Frontend

Next.js / React

Tailwind CSS

Axios

Backend

FastAPI

PostgreSQL

SQLAlchemy

JWT Authentication

WebSockets (real-time updates)

AI Services

Scikit-learn / Transformers

spaCy / Hugging Face

Sentiment Analysis Model

Priority Scoring Model

DevOps

Docker

Nginx

GitHub Actions (CI/CD)

AWS / Railway / Render

Project Structure
ps-crm/
│
├── backend/
│   ├── app/
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── ai_engine/
│   ├── database.py
│   └── main.py
│
├── frontend/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── utils/
│
├── docker-compose.yml
├── requirements.txt
└── README.md
Complete Setup Guide
1. Clone the Repository
git clone https://github.com/your-username/ps-crm.git
cd ps-crm
2. Backend Setup (FastAPI)
Create Virtual Environment
cd backend
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows
Install Dependencies
pip install -r requirements.txt
Configure Environment Variables

Create a .env file inside backend/:

DATABASE_URL=postgresql://username:password@localhost:5432/pscrm
SECRET_KEY=your_secret_key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=60
3. Database Setup (PostgreSQL)

Install PostgreSQL from the official website.

Create the database:

CREATE DATABASE pscrm;

Run migrations:

alembic upgrade head
4. Run Backend Server
uvicorn app.main:app --reload

Backend will run at:

http://127.0.0.1:8000

Swagger documentation:

http://127.0.0.1:8000/docs
5. Frontend Setup (Next.js)
cd ../frontend
npm install

Create .env.local:

NEXT_PUBLIC_API_URL=http://127.0.0.1:8000

Run frontend:

npm run dev

Frontend will run at:

http://localhost:3000
Docker Setup (Recommended)

From the root directory:

docker-compose up --build

This will:

Start backend service

Start frontend service

Launch PostgreSQL container

Default Roles

Citizen

Department Officer

Supervisor

Admin

AI Model Training (Optional)

Navigate to the AI module:

cd backend/ai_engine
python train_model.py

This generates:

priority_model.pkl
classification_model.pkl
Running Tests
pytest
Sample API Endpoints
Method	Endpoint	Description
POST	/complaints	Create complaint
GET	/complaints/{id}	Track complaint
PUT	/assign	Assign complaint
GET	/analytics	Retrieve dashboard metrics
POST	/auth/login	User authentication
Deployment Options
Render

Deploy backend as Web Service

Deploy frontend as Static Site

AWS

EC2 for backend

RDS for PostgreSQL

S3 for media storage

CloudFront for CDN

Roadmap

AI-based duplicate detection

WhatsApp bot integration

Officer performance scoring

Heatmap visualization

Predictive backlog risk engine

Public transparency dashboard