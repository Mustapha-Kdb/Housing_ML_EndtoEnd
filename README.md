# 🏠 Housing Regression - End-to-End ML Pipeline

<div align="center">

[![Python](https://img.shields.io/badge/-Python%203.11-000?&logo=python)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/-FastAPI-000?&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Streamlit](https://img.shields.io/badge/-Streamlit-FF4B4B?logo=streamlit&logoColor=white)](https://streamlit.io/)
[![XGBoost](https://img.shields.io/badge/-XGBoost-00A86B?logo=xgboost&logoColor=white)](https://xgboost.readthedocs.io/)
[![Docker](https://img.shields.io/badge/-Docker-2496ED?&logo=docker&logoColor=white)](https://www.docker.com/)
[![AWS](https://img.shields.io/badge/-AWS-232F3E?&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
[![GitHub Actions](https://github.com/Mustapha-Kdb/Housing_ML_EndtoEnd/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/Mustapha-Kdb/Housing_ML_EndtoEnd/actions/workflows/ci.yml)

</div>

---

## 📊 Project Overview

**Production-ready ML system** that predicts housing prices using XGBoost, with automated training pipelines, REST API, interactive dashboard, and cloud deployment.

### Key Highlights
- ✅ **Modular pipelines:** Feature engineering → Training → Inference
- ✅ **REST API & Dashboard:** FastAPI backend + Streamlit UI
- ✅ **Cloud-native:** AWS (S3, ECR, ECS) + Docker containers
- ✅ **Automated deployment:** GitHub Actions CI/CD pipeline
- ✅ **Production-grade:** Health checks, logging, error handling

---

## 🏗️ Architecture

```
Raw Data → Preprocessing → Feature Engineering → XGBoost Model
                                                        ↓
                                    ┌───────────────────┴───────────────────┐
                                    ↓                                       ↓
                          FastAPI (Port 8000)                    Streamlit (Port 8501)
                                  ECS Service                         ECS Service
```

---

## 🚀 Quick Start

### Local Development
```bash
# Install & run training
uv sync
python src/training_pipeline/train.py

# API
uv run uvicorn src.api.main:app --host 0.0.0.0 --port 8000

# Dashboard
streamlit run app.py --server.port 8501
```

### Cloud Deployment
```bash
# Push to main → GitHub Actions automatically:
# 1. Builds Docker images
# 2. Pushes to AWS ECR
# 3. Deploys to ECS (zero-downtime rolling update)

git commit -am "Update model"
git push origin main
```

---

## 📁 Core Components

| Component | Purpose | Tech |
|-----------|---------|------|
| **Feature Pipeline** | Data loading, cleaning, encoding | Pandas, Scikit-learn |
| **Training Pipeline** | Model training & hyperparameter tuning | XGBoost, Optuna, MLflow |
| **API** | Real-time predictions | FastAPI, Uvicorn |
| **Dashboard** | Interactive predictions & analytics | Streamlit, Plotly |
| **CI/CD** | Automated build & deployment | GitHub Actions, Docker |

---

## 🔧 Tech Stack

**Core:** Python 3.11 | XGBoost | FastAPI | Streamlit

**Cloud:** AWS (S3, ECR, ECS) | Docker | GitHub Actions

**Data:** Pandas | Scikit-learn | Great Expectations

**Tracking:** MLflow | Optuna

---

## 📋 Features

✅ Time-aware data splits (prevents leakage)  
✅ Automated hyperparameter tuning  
✅ RESTful API with schema validation  
✅ Interactive web dashboard  
✅ Health checks & monitoring  
✅ Batch prediction processing  
✅ S3-backed model storage  
✅ Comprehensive test suite  

---

## 🌐 API Endpoints

**Base:** `http://<host>:8000`

- `GET /` → Health check
- `GET /health` → Detailed status
- `POST /predict` → Batch predictions
- `GET /latest_predictions` → Recent results

---

## 🧪 Testing

```bash
pytest                    # Run all tests
pytest -v --cov=src     # With coverage
```

---

## 📊 Project Structure

```
├── src/
│   ├── feature_pipeline/       # Data loading & preprocessing
│   ├── training_pipeline/      # Model training & tuning
│   ├── inference_pipeline/     # Production inference
│   └── api/                    # FastAPI service
├── app.py                      # Streamlit dashboard
├── tests/                      # Test suite
├── data/                       # Datasets (train/eval/holdout)
├── models/                     # Trained models & encoders
├── .github/workflows/ci.yml    # CI/CD pipeline
└── pyproject.toml             # Dependencies (uv)
```

---

## ☁️ Cloud Deployment

**AWS Infrastructure:**
- **ECS Cluster:** `housing-api-cluster-ecs` (Fargate)
- **ECR Repositories:** API & Streamlit images
- **S3 Bucket:** Models & data storage
- **Auto-scaling:** Dynamic task scaling

**Deployment Process:**
```
Push to main → GitHub Actions → Build images → Push to ECR → Deploy to ECS
```

---

## 🎯 What's Demonstrated

- ✅ Full ML lifecycle (data → model → production)
- ✅ Software engineering best practices (modular code, testing)
- ✅ DevOps & cloud infrastructure (AWS, Docker, CI/CD)
- ✅ API design & microservices architecture
- ✅ Data quality & leakage prevention
- ✅ Model tracking & experiment management

---

## 📚 Common Commands

```bash
uv sync                              # Install deps
python src/training_pipeline/train.py    # Train model
mlflow ui                            # View experiments
pytest -v                            # Run tests
docker build -t housing-api .        # Build image
```
