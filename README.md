# 🧠 MindPulse AI

### 📊 Predicting Student Wellness Signals from Everyday Habits

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Science-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![HTML5](https://img.shields.io/badge/HTML5-Frontend-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-Styling-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Render](https://img.shields.io/badge/Deployed%20on-Render-46E3B7?logo=render&logoColor=black)](https://render.com/)

---

## 🌟 What is MindPulse AI?

**MindPulse AI** is a machine-learning-powered web application that estimates a student's **Wellness Signal Score from 0–10** using everyday lifestyle and academic habits.

The idea is simple:

> 📱 How much time do you spend on your phone?
> 😴 How much do you sleep?
> 📚 How many hours do you study?
> 🏃 How physically active are you?
> 😟 What is your stress level?

MindPulse AI combines these signals with additional student information and uses a trained machine learning model to generate a predicted wellness score.

The project includes a **FastAPI backend**, a **custom vanilla HTML/CSS/JavaScript frontend** (with light/dark mode), and a **scikit-learn machine learning pipeline**.

### 🚀 Try the Live Demo

**👉 https://mindpulse-ai-1-1gav.onrender.com**

---

## ✨ Features

* 🧠 Machine-learning-based wellness score prediction
* 📈 Predicts a score between **0 and 10**
* 🎓 Designed around student lifestyle and academic habits
* ⚡ FastAPI-powered prediction API with a `/health` check endpoint
* 🌗 Light & dark mode toggle
* 💻 Clean frontend built without React, Vue, or other frameworks
* 📊 Model comparison using multiple regression approaches
* 🔬 Trained on **5,000 student survey records**
* ☁️ Deployed on **Render**
* 📦 Saved scikit-learn pipeline for predictions

---

## 🧩 How It Works

The application follows a straightforward ML workflow:

```text
┌──────────────────────┐
│   Student Inputs      │
│                       │
│ Age                   │
│ Gender                │
│ Academic Level        │
│ Screen Time           │
│ Sleep Hours           │
│ Study Hours           │
│ Physical Activity     │
│ Stress Level          │
│ + Other Features      │
└──────────┬────────────┘
           │
           ▼
┌──────────────────────┐
│   FastAPI Backend     │
│                       │
│ Validate input        │
│ with Pydantic         │
└──────────┬────────────┘
           │
           ▼
┌──────────────────────┐
│   ML Pipeline         │
│                       │
│ Random Forest         │
│ Regressor             │
└──────────┬────────────┘
           │
           ▼
┌──────────────────────┐
│   Wellness Signal     │
│   Score: 0 – 10       │
└──────────────────────┘
```

The frontend collects the student's information and sends it to the FastAPI backend. The backend validates the request with Pydantic and passes the data to the saved machine learning pipeline.

---

## 📊 Dataset

MindPulse AI was trained using:

**`Student_Social_Media_And_Mental_Health_Impact.csv`**

| Dataset Detail  |      Value |
| --------------- | ---------: |
| 👥 Records      |      5,000 |
| 📋 Columns      |         13 |
| 🎯 Task         | Regression |
| 🔀 Test Split   |        30% |
| 🎲 Random State |         42 |

### 🔍 Features Used

The model uses **12 features**:

|  # | Feature                   |
| -: | ------------------------- |
|  1 | Age                       |
|  2 | Gender                    |
|  3 | Country — grouped         |
|  4 | Academic Level            |
|  5 | Most-Used Platform        |
|  6 | Purpose of Use            |
|  7 | Average Daily Screen Time |
|  8 | Daily Phone Unlocks       |
|  9 | Study Hours               |
| 10 | Physical Activity Hours   |
| 11 | Sleep Hours               |
| 12 | Stress Level              |

These features are passed through the trained preprocessing/model pipeline before generating the prediction.

---

## 🤖 Model Comparison

Three regression approaches were evaluated using a **30% test split** with `random_state=42`.

| Model                          | Test R² ↑ |     MAE ↓ |    RMSE ↓ |
| ------------------------------ | --------: | --------: | --------: |
| 📐 Linear Regression           |     0.740 |     0.536 |     0.676 |
| 🌲 **Random Forest (Default)** | **0.878** | **0.347** | **0.463** |
| ⚙️ Random Forest (Tuned)       |     0.865 |     0.369 |     0.487 |

### 🏆 Shipped Model

**Random Forest (Default)** is the model shipped with MindPulse AI.

It achieved the strongest test performance among the three evaluated models:

* **R²:** `0.878`
* **MAE:** `0.347`
* **RMSE:** `0.463`

Interestingly, the tuned Random Forest performed slightly worse on the held-out test set than the default Random Forest, so the **default Random Forest was selected for deployment**.

---

## 🛠️ Tech Stack

### 🧠 Machine Learning

* Python
* scikit-learn
* pandas
* joblib

### ⚡ Backend

* FastAPI
* Pydantic

### 🎨 Frontend

* HTML5
* CSS3
* Vanilla JavaScript

No frontend framework is required.

### ☁️ Deployment

* Render

---

## 📁 Project Structure

```text
MindPulse-AI/
│
├── app.py
├── index.html
├── style.css
├── script.js
│
├── ML_Project.ipynb
├── Mental_Health_Model.pkl
│
├── Student_Social_Media_And_Mental_Health_Impact.csv
├── requirements.txt
│
└── README.md
```

### 📌 File Overview

| File                                                | Purpose                                     |
| --------------------------------------------------- | ------------------------------------------- |
| `app.py`                                            | FastAPI backend and prediction API          |
| `index.html`                                        | Web application's HTML structure            |
| `style.css`                                         | Frontend styling                            |
| `script.js`                                         | Frontend interaction and API communication  |
| `ML_Project.ipynb`                                  | Model training and experimentation notebook |
| `Mental_Health_Model.pkl`                           | Saved machine learning pipeline             |
| `requirements.txt`                                  | Python dependencies                         |
| `Student_Social_Media_And_Mental_Health_Impact.csv` | Training dataset                            |
| `README.md`                                         | Project documentation                       |

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Poojarautela03/MindPulse-AI.git
cd MindPulse-AI
```

### 2️⃣ Create a Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Run the FastAPI Application

```bash
uvicorn app:app --reload
```

The application should be available at:

```text
http://127.0.0.1:8000
```

Open `index.html` separately in your browser for the frontend (update `API_BASE` in `script.js` if not pointing at the deployed Render URL).

---

## 🌐 API Usage

MindPulse AI exposes a prediction endpoint through FastAPI.

### 📤 Example Request

```http
POST /predict
Content-Type: application/json
```

Example request body:

```json
{
  "age": 20,
  "gender": "Female",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Entertainment",
  "avg_daily_usage_hours": 5.5,
  "daily_unlocks": 80,
  "study_hours": 4,
  "physical_activity_hours": 1.5,
  "sleep_hours_per_night": 7,
  "stress_level": "Medium"
}
```

### 📥 Example Response

```json
{
  "predicted_mental_health_score": 7.42
}
```

### ❤️ Health Check

```http
GET /health
```

```json
{
  "status": "ok",
  "model_loaded": true
}
```

---

## 🧪 Model Training

The model development process is documented in:

```text
ML_Project.ipynb
```

The notebook covers data preprocessing, the feature pipeline, and model evaluation/comparison.

The resulting trained pipeline is stored as:

```text
Mental_Health_Model.pkl
```

The deployed FastAPI application loads this saved pipeline to generate predictions.

---

## 💡 Why This Project?

Students deal with a combination of academic demands, screen exposure, sleep patterns, physical activity, and stress.

MindPulse AI explores whether these everyday signals can be used to estimate a simple **wellness signal score** through machine learning.

The goal isn't to reduce mental well-being to a single number. Instead, this project demonstrates how **data science, machine learning, APIs, and frontend development** can come together to build an accessible student-focused application.

---

## ⚠️ Disclaimer

### 💙 Important

**MindPulse AI is an informational machine-learning project, not a clinical or diagnostic tool.**

The predicted Wellness Signal Score should **not** be treated as a medical diagnosis, psychological assessment, or substitute for professional advice.

Mental health is complex, and a numerical prediction cannot capture someone's complete well-being. If you are concerned about your mental health or well-being, consider reaching out to a qualified mental-health professional or someone you trust.

---

## 🌐 Live Demo

Try MindPulse AI here:

**🔗 https://mindpulse-ai-1-1gav.onrender.com**

---

## 📈 Future Improvements

Some potential directions for future versions include:

* 📊 More detailed prediction insights
* 📉 Visualizations of lifestyle factors
* 🔍 Better model interpretability
* 🧪 Additional model validation
* 📱 Improved mobile experience
* 🔄 More diverse training data

---

## ⭐ Support the Project

If you found **MindPulse AI** interesting or useful, consider giving the repository a ⭐ star!

It helps support the project and motivates further improvements.

---

## 👩‍💻 Made by Pooja Rautela

Built with ❤️ using **Python, Machine Learning, FastAPI, and Vanilla JavaScript**.

⭐ **If you like MindPulse AI, don't forget to star the repo!**
