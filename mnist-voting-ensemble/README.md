📚 Available languages: [English](README.md) | [فارسی](README.fa.md)

# 🧠 MNIST Voting Ensemble Classifier

A complete end-to-end project for handwritten digit recognition (MNIST) using both machine learning and deep learning. This system includes training, model tracking, ensemble inference, authentication, API access, and Docker deployment.

## 🔍 Features

- Train multiple models (Simple CNN, Deep CNN, CNN with BatchNorm, SVM)
- Monitor training process using **MLflow**
- Select the best models and perform **weighted voting ensemble** based on accuracy
- Provide prediction API using **FastAPI**
- Web interface with **Bootstrap**
- User authentication system using **JWT tokens**
- Deployable locally or on any server using **Docker**

## 🛠 Tech Stack

- Python 3, PyTorch, Scikit-learn
- MLflow
- FastAPI
- SQLite + JWT
- Bootstrap 5
- Docker
- Google Colab (for training)

## 📁 Project Structure

```
mnist-voting-ensemble/
├── models/             # Saved models
├── mlruns/             # MLflow logs
├── notebooks/          # Google Colab notebooks
├── app/                # FastAPI backend
├── frontend/           # HTML templates (Bootstrap)
├── Dockerfile
├── requirements.txt
└── README.md
```

## 🚀 Getting Started

### 1. Train Models

Train models in Google Colab using the notebook provided under:
```
notebooks/train_models.ipynb
```
All experiments will be tracked via MLflow.

### 2. Run API Locally

```bash
uvicorn app.main:app --reload
```

### 3. Dockerize the App

```bash
docker build -t mnist-app .
docker run -p 8000:8000 mnist-app
```

### 4. Access the API

Visit the FastAPI documentation at:
```
http://localhost:8000/docs
```

## 📦 API Functionality

- `/register`: User signup
- `/login`: JWT-based login
- `/predict`: Upload image and get prediction (requires token)
- Rate-limiting or usage tokens to restrict requests

## 🧠 Model Ensemble

- Each model predicts a class or probability distribution
- Weighted voting is applied based on each model's validation accuracy
- Final output is the class with the highest weighted score

## 🌐 Frontend (Bootstrap)

- Login and registration pages
- Image upload and digit prediction
- Displays the predicted result with basic UI styling

## ✅ Authentication

- Users must login to access prediction functionality
- Secure JWT token is returned on login
- Token must be attached to subsequent requests

---
