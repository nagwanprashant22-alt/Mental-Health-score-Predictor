Mental Health Score Predictor

An end-to-end machine learning web application that estimates a mental health score from a student's lifestyle, academic routine, social-media habits, sleep, physical activity, and perceived stress.

Disclaimer: This project is intended for educational and informational purposes only. It is not a clinical assessment, medical diagnosis, or substitute for professional mental-health advice.

Features

Collects academic, lifestyle, and social-media usage information through a responsive web interface

Validates incoming data with Pydantic

Generates predictions using a trained scikit-learn pipeline

Serves predictions through a FastAPI REST API

Displays the predicted score on a 0–10 scale

Supports separate frontend and backend deployment

Includes automatic interactive API documentation through Swagger UI

Tech Stack

Machine learning: Python, pandas, scikit-learn, joblib

Backend: FastAPI, Pydantic, Uvicorn

Frontend: HTML5, CSS3, JavaScript

Model development: Jupyter Notebook

Deployment: Render

Project Structure

Mental-Health-score-Predictor/
├── index.html
├── style.css
├── script.js
├── main.py
├── Mental_Health_Model.pkl
├── ML_Project.ipynb
├── Student Social Media And Mental Health Impact.csv
├── requirements.txt
├── .gitignore
└── README.md

How It Works

The user enters profile, academic, digital-habit, lifestyle, and stress information.

The frontend validates the form and sends a JSON request to the FastAPI backend.

Pydantic validates the incoming request.

The backend converts the request into a pandas DataFrame.

The saved scikit-learn pipeline preprocesses the data and generates a prediction.

The API returns the predicted mental health score to the frontend.

Input Features

Age

Gender

Country

Academic level

Most-used social-media platform

Primary purpose of social-media use

Average daily usage

Daily phone unlocks

Study hours

Physical activity

Sleep duration

Perceived stress level

Run Locally

1. Clone the repository

git clone https://github.com/nagwanprashant22-alt/Mental-Health-score-Predictor.git
cd Mental-Health-score-Predictor

2. Create and activate a virtual environment

Windows PowerShell:

python -m venv .venv
.\.venv\Scripts\Activate.ps1

macOS/Linux:

python3 -m venv .venv
source .venv/bin/activate

3. Install dependencies

python -m pip install -r requirements.txt

4. Start the backend

python -m uvicorn main:app --reload

The backend will be available at:

http://127.0.0.1:8000

Interactive API documentation:

http://127.0.0.1:8000/docs

5. Start the frontend

Open the project with VS Code and use the Live Server extension to launch index.html.

Before local frontend testing, set the API base URL in script.js to:

const API_BASE = "http://127.0.0.1:8000";

API

POST /predict

Example request:

{
  "age": 28,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Entertainment",
  "avg_daily_usage_hours": 9,
  "daily_unlocks": 100,
  "study_hours": 2,
  "physical_activity_hours": 0,
  "sleep_hours_per_night": 4,
  "stress_level": "High"
}

Example response:

{
  "predicted_mental_health_score": 5.06
}


Limitations

Predictions depend on the quality and representativeness of the training data.

The score is a statistical estimate and must not be interpreted as a diagnosis.

Self-reported user inputs may be incomplete or inaccurate.

The model should be evaluated for bias before use with populations not represented in the dataset.

Author

Prashant Kumar Nagwan

GitHub: nagwanprashant22-alt

LinkedIn: Prashant Kumar Nagwan