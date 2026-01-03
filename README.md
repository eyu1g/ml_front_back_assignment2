# ML Heart Disease Prediction App

A full-stack machine learning application for predicting heart disease using Logistic Regression and Decision Tree models.

## Project Structure

```
ml/
├── ml-frontend/          # Frontend (HTML/CSS/JavaScript)
│   ├── index.html
│   ├── script.js
│   └── styles.css
├── ml-fastapi-backend/   # Backend (FastAPI)
│   ├── main.py
│   ├── requirements.txt
│   ├── decision_tree_model.joblib
│   ├── logistic_model.joblib
│   └── scaler.joblib
└── README.md
```

## Frontend Deployment (Vercel)

The frontend is deployed on Vercel at: `https://ml-frontend-c716.vercel.app`

### Deployment Steps:
1. Connect your GitHub repository to Vercel
2. Set the root directory to `ml-frontend`
3. Deploy automatically on push to main branch

## Backend Deployment (Render)

The backend is deployed on Render and provides the API endpoints.

### Deployment Steps:
1. Connect your GitHub repository to Render
2. Set the root directory to `ml-fastapi-backend`
3. Set the build command: `pip install -r requirements.txt`
4. Set the start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`
5. Deploy automatically on push to main branch

## API Endpoints

### POST /predict
Predicts heart disease based on input features.

**Request Body:**
```json
{
  "features": [age, sex, cp, trestbps, chol, fbs, restecg, thalach, exang, oldpeak, slope, ca, thal],
  "model": "Logistic Regression" | "Decision Tree"
}
```

**Response:**
```json
{
  "prediction": 0 | 1
}
```

## Local Development

### Frontend
```bash
cd ml-frontend
# Use any live server or open index.html in browser
```

### Backend
```bash
cd ml-fastapi-backend
pip install -r requirements.txt
uvicorn main:app --reload
```

## Features

- Heart disease prediction using two ML models
- Responsive web interface
- RESTful API with FastAPI
- CORS enabled for cross-origin requests
- Deployed on Vercel (frontend) and Render (backend)
