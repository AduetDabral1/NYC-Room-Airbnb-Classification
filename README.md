# ML-Powered NYC Airbnb Room Type Predictor

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

### Machine Learning

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

### Backend

- FastAPI
- Pydantic

### Frontend

- HTML
- CSS
- JavaScript

### Deployment

- Render
- GitHub

---

## Project Workflow

The project is organized into five main stages.

### 1. Machine Learning

The notebook handles the machine learning workflow:

- Load and explore the Airbnb dataset
- Clean and prepare the data
- Engineer relevant features
- Train classification models
- Compare model performance
- Tune the selected model
- Evaluate the final model
- Save the trained pipeline

The notebook uses classification models including Logistic Regression, Decision Tree, Random Forest, and Gradient Boosting.

---

### 2. FastAPI

FastAPI provides the application layer around the trained model.

Its role is to:

- Receive prediction requests
- Validate incoming data
- Load the trained model
- Generate predictions
- Return prediction results

This keeps the machine learning workflow separate from the web application.

The project execution plan identifies FastAPI as the layer that turns the trained model into a service that other applications can interact with. fileciteturn1file1L114-L130

---

### 3. Saved Model

The trained machine learning pipeline is saved as a reusable Joblib artifact.

This allows the application to load an already-trained model instead of retraining it whenever a prediction is requested.

The execution plan describes this stage as packaging the trained model so it can be reused by the application. fileciteturn1file1L132-L148

---

### 4. Web Interface

A lightweight browser interface provides a simple way for users to interact with the prediction service.

The interface uses:

- HTML
- CSS
- JavaScript

The frontend communicates with the API and displays the prediction to the user. The project execution plan intentionally keeps this layer lightweight rather than introducing a frontend framework. fileciteturn1file4L411-L417

---

### 5. Deployment

The application is designed for deployment using Render.

The execution plan describes the deployment as two parts:

- **Static Site** — web interface
- **Web Service** — FastAPI application and model

This turns the local machine learning project into an application that can be accessed remotely. fileciteturn1file4L420-L435

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

### Components

**`Classification_Notebook.ipynb`**

Contains the machine learning workflow and model training process.

**`Model_Pipeline.pkl`**

Contains the trained model pipeline used for predictions.

**`app/main.py`**

Application entry point and API routes.

**`app/schemas.py`**

Request and response validation models.

**`app/services/predictor.py`**

Model loading and prediction logic.

**`static/`**

Contains the browser interface.

**`requirements.txt`**

Contains the Python dependencies required to run the application.

---

## Architecture

```text
                  ┌─────────────────────┐
                  │   Web Interface     │
                  │ HTML / CSS / JS     │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │      FastAPI        │
                  │   API / Validation  │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │   Predictor Service │
                  │  Model Inference    │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │  Model_Pipeline.pkl │
                  └─────────────────────┘
```

The separation keeps the application responsibilities clear:

- **Frontend** handles user interaction.
- **FastAPI** handles HTTP requests.
- **Schemas** handle request/response validation.
- **Predictor service** handles model inference.
- **Saved pipeline** performs the trained ML transformation and prediction.

The project execution plan follows the same overall progression from machine learning to FastAPI, saved model, interface, and deployment. fileciteturn1file0L92-L101

---

## Model

The target variable is:

```text
room_type
```

The notebook evaluates multiple classification approaches and uses cross-validation and **macro-F1** as an important comparison metric because the target classes are imbalanced.

The final trained pipeline is saved with Joblib for application use.

---

## Running the Project

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run the API

```bash
uvicorn app.main:app --reload
```

The exact command may differ depending on the final application entry point.

### Open the interface

Once the application is running, open the browser interface and submit listing information to receive a predicted room type.

---

## Deployment

The intended deployment architecture is:

```text
GitHub
   │
   ├── Static Site
   │      └── HTML / CSS / JavaScript
   │
   └── Web Service
          └── FastAPI + Model
```

The project execution plan identifies Render as the deployment platform and describes the interface and API/model as separate deployment components. fileciteturn1file4L420-L435

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
