# ML-Powered NYC Airbnb Room Type Predictor

Live Project - https://nyc-room-airbnb-classification-1.onrender.com

## Overview

This project is a machine learning application that predicts the **room type** of an Airbnb listing in New York City.

The project covers the complete workflow from:

**Data → Machine Learning → API → Web Interface → Deployment**

The model is trained using the NYC Airbnb Open Data dataset and predicts one of three room types:

- `Entire home/apt`
- `Private room`
- `Shared room`

> **Note:** The uploaded notebook and project execution plan describe an NYC Airbnb room-type classification project. They do not describe the Student Mental Health Score Predictor referenced in the earlier README text.

---

## Features

- Airbnb room-type prediction
- Exploratory data analysis and data preparation
- Machine learning classification
- Model comparison and tuning
- Saved model pipeline for inference
- FastAPI-based prediction service
- Browser-based interface
- Render deployment architecture

---

## Tech Stack

| Category | Technologies |
|---|---|
| **Machine Learning** | Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Joblib |
| **Backend** | FastAPI, Pydantic |
| **Frontend** | HTML, CSS, JavaScript |
| **Deployment** | Render, GitHub |

---

## Project Workflow

The project is organized into five main stages.

#### 1. Machine Learning Notebook

#### 2. FastAPI

#### 3. Saved Model

#### 4. Web Interface

#### 5. Deployment


---


## Architecture

<img width="520" height="675" alt="image" src="https://github.com/user-attachments/assets/05d9896b-cb1b-4363-b0b4-d3d307dc8313" />


The separation keeps the application responsibilities clear:

- **Frontend** handles user interaction.
- **FastAPI** handles HTTP requests.
- **Schemas** handle request/response validation.
- **Predictor service** handles model inference.
- **Saved pipeline** performs the trained ML transformation and prediction.

The project execution plan follows the same overall progression from machine learning to FastAPI, saved model, interface, and deployment.


---

## Project Structure

A modular structure for the application is:

```text
.
├── Classification_Notebook.ipynb
├── Model_Pipeline.pkl
│
├── app/
│   ├── main.py
│   ├── schemas.py
│   └── services/
│       └── predictor.py
│
├── static/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── requirements.txt
└── README.md
```

---

## Model

The target variable is:

```text
room_type
```

The notebook evaluates multiple classification approaches and uses cross-validation and **macro-F1** as an important comparison metric because the target classes are imbalanced.

The final trained pipeline is saved with Joblib for application use.

---

## Limitations

- The model is trained on the supplied NYC Airbnb dataset and may not generalize to other locations or future datasets.
- The `Shared room` class is relatively uncommon compared with the other room types.
- Model performance depends on the quality and characteristics of the training data.
- The uploaded project documentation does not include the final FastAPI source, frontend source, deployment configuration, or live application URL, so those details are not specified here.

---

## Future Improvements

- Add automated unit and API tests
- Improve model monitoring
- Track model and dataset versions
- Add prediction logging
- Evaluate performance on newer data
- Add model explainability
- Improve the frontend experience
- Add CI/CD for automated testing and deployment

---

## Project Execution Plan

The accompanying `Project_Execution_Plan.html` presents the project as an interactive five-stage journey:

1. **Machine Learning**
2. **FastAPI**
3. **Python Pickle / Joblib**
4. **Interface**
5. **Deployment on Render**

The HTML provides navigation between these stages and a final project recap. fileciteturn1file5L491-L519

---

## Disclaimer

This project is an educational machine learning application. Predictions are model-generated estimates based on historical Airbnb data and should not be treated as guaranteed classifications.
