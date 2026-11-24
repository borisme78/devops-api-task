# DevOps API Task: React + Python (Flask) REST API

Market admin panel: React frontend and Flask REST API backend (SQLite).
Tested on a local PC (macOS) with curl and Postman.

## Structure
```
devops_task_api/
├── python-backend/   # Flask REST API, port 5000
└── react/            # React frontend, port 3000
```

## Requirements
- Git, Node.js and npm, Python 3.12

## Backend (Python)
```bash
git clone https://github.com/devops-fundamentals-templates/python-backend.git
cd python-backend
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python db.py -a
python app.py
```
The API runs at http://localhost:5000

## Test with curl
```bash
curl -i http://localhost:5000/api/products
curl -i -X POST http://localhost:5000/api/products \
  -H "Content-Type: application/json" \
  -d '{"name":"Tea","price":45}'
```

## Test with Postman
- GET `http://localhost:5000/api/products`
- POST `http://localhost:5000/api/products`, Body: raw, JSON, `{"name":"Laptop","price":15000}`

## Frontend (React)
```bash
git clone https://github.com/devops-fundamentals-templates/react.git
cd react
npm install
cp .env.example .env     # REACT_APP_BASE_URL=http://localhost:5000/api
npm start
```
The app runs at http://localhost:3000 (the backend must be running).

