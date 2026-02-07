# Kidney Disease Prediction System - Setup Guide

## Overview
This is a full-stack web application for predicting kidney disease using machine learning. The system consists of a Flask backend and a React frontend.

## Prerequisites
- Python 3.8 or higher
- Node.js 16 or higher
- npm or yarn

## Backend Setup (Flask)

### 1. Navigate to backend directory
```bash
cd backend
```

### 2. Create virtual environment (recommended)
```bash
python -m venv venv
```

### 3. Activate virtual environment
- Windows: `venv\Scripts\activate`
- macOS/Linux: `source venv/bin/activate`

### 4. Install dependencies
```bash
pip install -r requirements.txt
```

### 5. Run the Flask server
```bash
python app.py
```

The backend will start on `http://127.0.0.1:5000`

## Frontend Setup (React)

### 1. Navigate to project root directory
```bash
cd ..
```

### 2. Install dependencies
```bash
npm install
```

### 3. Run the development server
```bash
npm run dev
```

The frontend will start on `http://localhost:5173` (or another port if 5173 is busy)

## Usage

1. Start the Flask backend server first (port 5000)
2. Start the React frontend server (port 5173)
3. Open your browser and navigate to the frontend URL
4. Navigate to the "Validation/Results" tab
5. Enter patient medical parameters:
   - Patient ID
   - Age
   - Sugar Level (su)
   - Sodium (sod)
   - Potassium (pot)
   - Red Blood Cell Count (rc)
6. Click "Predict" to get the prediction result
7. View the results with color-coded indicators and probability distribution

## Sample Test Data

You can use these sample values for testing:

**Healthy Patient Example:**
- Patient ID: 250
- Age: 40
- Sugar Level: 0
- Sodium: 140
- Potassium: 5
- Red Blood Cell Count: 5

**Patient with Kidney Disease Example:**
- Patient ID: 0
- Age: 48
- Sugar Level: 0
- Sodium: 0
- Potassium: 0
- Red Blood Cell Count: 5.2

## Features

- **Home**: Overview of the project and its goals
- **About Project**: Technology stack and key features
- **Objectives**: Main objectives of the system
- **Procedure/Architecture**: System workflow and architecture
- **Validation/Results**: Interactive prediction interface

## Troubleshooting

### Backend Issues
- **Model not loading**: Ensure `model.pkl` is in the `backend` directory
- **Port already in use**: Change the port in `app.py` (line: `app.run(debug=True, port=5000)`)
- **CORS errors**: Verify Flask-CORS is installed and configured

### Frontend Issues
- **Cannot connect to backend**: Ensure Flask server is running on port 5000
- **Build errors**: Run `npm install` to ensure all dependencies are installed
- **Port conflicts**: Vite will automatically use another port if 5173 is busy

## API Endpoints

### POST /predict
Predicts kidney disease based on patient parameters.

**Request Body:**
```json
{
  "id": 0,
  "age": 48,
  "su": 0,
  "sod": 140,
  "pot": 5,
  "rc": 5.2
}
```

**Response:**
```json
{
  "prediction": "Kidney Disease Detected",
  "has_disease": true,
  "confidence": 95.5,
  "disease_probability": 95.5,
  "healthy_probability": 4.5
}
```

### GET /health
Health check endpoint to verify backend is running.

**Response:**
```json
{
  "status": "healthy",
  "model_loaded": true
}
```

## Project Structure

```
project/
├── backend/
│   ├── app.py              # Flask application
│   ├── model.pkl           # Trained ML model
│   └── requirements.txt    # Python dependencies
├── src/
│   ├── components/         # React components
│   │   ├── Navigation.tsx
│   │   ├── Home.tsx
│   │   ├── About.tsx
│   │   ├── Objectives.tsx
│   │   ├── Procedure.tsx
│   │   ├── Validation.tsx
│   │   └── Footer.tsx
│   ├── App.tsx            # Main application component
│   └── main.tsx           # Application entry point
└── package.json           # Node dependencies
```

## Technologies Used

### Backend
- Flask - Web framework
- Flask-CORS - Cross-origin resource sharing
- NumPy - Numerical computing
- Scikit-learn - Machine learning

### Frontend
- React - UI library
- TypeScript - Type-safe JavaScript
- Tailwind CSS - Styling
- Lucide React - Icons
- Vite - Build tool

## Notes

- The system uses a Random Forest Classifier trained on kidney disease data
- Predictions are based on 6 key medical parameters
- The model provides probability scores for both disease and healthy states
- All communications between frontend and backend use JSON format
- The dark theme is optimized for better visibility and reduced eye strain
