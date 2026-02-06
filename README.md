<div align="center">

# 🏠 Machine Learning Workflow System
### Production-Grade House Price Prediction Pipeline

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![MLflow](https://img.shields.io/badge/MLflow-Experiment%20Tracking-0194E2?logo=mlflow)](https://mlflow.org/)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/vinodbavage31/MachineLearning-Workflow-system/issues)

![Profile Views](https://komarev.com/ghpvc/?username=vinodbavage31&repo=MachineLearning-Workflow-system&color=blue&style=flat-square&label=Profile+Views)

---

**[Features](#-key-features) • [Quick Start](#-quick-start) • [Architecture](#-project-architecture) • [Documentation](#-documentation) • [Contributing](#-contributing)**

---

</div>

## 📋 Table of Contents

- [Overview](#-overview)
- [Why This Project?](#-why-this-project)
- [Key Features](#-key-features)
- [Project Architecture](#-project-architecture)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
- [Usage](#-usage)
  - [Training Pipeline](#training-pipeline)
  - [Prediction](#prediction)
  - [MLflow Tracking](#mlflow-tracking)
- [Project Structure](#-project-structure)
- [Pipeline Workflow](#-pipeline-workflow)
- [Model Performance](#-model-performance)
- [Documentation](#-documentation)
- [Contributing](#-contributing)
- [Roadmap](#-roadmap)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 Overview

**MachineLearning-Workflow-System** is an industry-standard machine learning project demonstrating **production-grade ML pipeline architecture** for house price prediction using the Ames Housing Dataset. Unlike traditional Jupyter notebook-based projects, this implementation showcases **clean code principles**, **modular design**, and **enterprise-level workflow practices** used in real-world ML systems.

### 🎓 Educational Focus

This project serves as a **comprehensive learning resource** for aspiring ML engineers and data scientists who want to understand how to build **scalable, maintainable, and production-ready** machine learning systems.

---

## 💡 Why This Project?

### Industry-Standard Practices

- **Modular Architecture**: Organized codebase with clear separation of concerns
- **Reusable Components**: Object-oriented design for code reusability
- **Pipeline-Based Workflow**: Automated, reproducible ML pipelines
- **Experiment Tracking**: MLflow integration for model versioning and monitoring
- **Configuration Management**: YAML-based config for easy experimentation
- **Clean Code**: Follows PEP 8 and software engineering best practices

### Learning Outcomes

✅ Understand production ML project structure  
✅ Learn to build modular, reusable ML pipelines  
✅ Master experiment tracking with MLflow  
✅ Implement data versioning and preprocessing workflows  
✅ Apply OOP principles to machine learning projects  
✅ Practice industry-standard code organization  

---

## ✨ Key Features

<table>
<tr>
<td width="50%">

### 🏗️ Architecture
- **Modular Pipeline Design**
- **OOP-Based Components**
- **Configuration-Driven Workflow**
- **Separation of Concerns**

</td>
<td width="50%">

### 🔬 ML Operations
- **MLflow Experiment Tracking**
- **Model Versioning**
- **Automated Data Pipelines**
- **Reproducible Workflows**

</td>
</tr>
<tr>
<td width="50%">

### 📊 Data Management
- **Data Ingestion Pipeline**
- **Feature Engineering Steps**
- **Data Validation**
- **Preprocessing Automation**

</td>
<td width="50%">

### 🚀 Deployment Ready
- **Sample Prediction Scripts**
- **Model Serialization**
- **Inference Pipeline**
- **Production-Ready Structure**

</td>
</tr>
</table>

---

## 🏛️ Project Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Configuration Layer                       │
│                      (config.yaml)                          │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                    Pipeline Orchestrator                     │
│                   (run_pipeline.py)                         │
└──────────────────────┬──────────────────────────────────────┘
                       │
       ┌───────────────┼───────────────┬──────────────────┐
       │               │               │                  │
       ▼               ▼               ▼                  ▼
┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────────┐
│   Data   │   │ Feature  │   │  Model   │   │    Model     │
│Ingestion │──▶│Engineering──▶│ Training │──▶│  Evaluation  │
└──────────┘   └──────────┘   └──────────┘   └──────────────┘
       │               │               │                  │
       └───────────────┴───────────────┴──────────────────┘
                       │
                       ▼
              ┌─────────────────┐
              │  MLflow Tracking │
              │  (Experiments &  │
              │   Model Registry)│
              └─────────────────┘
                       │
                       ▼
              ┌─────────────────┐
              │   Deployment    │
              │ (run_deployment │
              │sample_predict)  │
              └─────────────────┘
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/vinodbavage31/MachineLearning-Workflow-system.git
   cd MachineLearning-Workflow-system
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

### Configuration

Edit `config.yaml` to customize pipeline parameters:

```yaml
# Example configuration
data:
  raw_data_path: "data/raw/"
  processed_data_path: "data/processed/"
  
model:
  algorithm: "linear_regression"
  test_size: 0.2
  random_state: 42
  
mlflow:
  experiment_name: "house_price_prediction"
  tracking_uri: "mlruns/"
```

---

## 📖 Usage

### Training Pipeline

Run the complete ML pipeline from data ingestion to model training:

```bash
python run_pipeline.py
```

This executes:
1. Data ingestion and extraction
2. Data cleaning and validation
3. Feature engineering
4. Model training
5. Model evaluation
6. Experiment logging to MLflow

### Prediction

Make predictions on new data:

```bash
python sample_predict.py
```

Or for deployment:

```bash
python run_deployment.py
```

### MLflow Tracking

Launch MLflow UI to view experiments and model performance:

```bash
mlflow ui
```

Then navigate to `http://localhost:5000` in your browser.

---

## 📁 Project Structure

```
MachineLearning-Workflow-system/
│
├── analysis/                  # Exploratory data analysis notebooks
│
├── config.yaml               # Pipeline configuration file
│
├── data/                     # Data directory
│   ├── raw/                 # Raw dataset
│   └── processed/           # Processed data
│
├── extracted_data/          # Extracted features
│
├── explanations/            # Documentation and explanations
│
├── mlruns/                  # MLflow experiment tracking data
│
├── pipelines/               # Pipeline orchestration modules
│   ├── training_pipeline.py
│   └── deployment_pipeline.py
│
├── src/                     # Source code
│   ├── data_ingestion/     # Data loading modules
│   ├── data_cleaning/      # Data preprocessing modules
│   ├── feature_engineering/ # Feature creation modules
│   ├── model_training/     # Model training modules
│   └── model_evaluation/   # Evaluation metrics modules
│
├── steps/                   # Individual pipeline steps
│   ├── ingest_data.py
│   ├── clean_data.py
│   ├── feature_engineering.py
│   ├── train_model.py
│   └── evaluate_model.py
│
├── tests/                   # Unit and integration tests
│
├── run_pipeline.py          # Main pipeline execution script
├── run_deployment.py        # Deployment script
├── sample_predict.py        # Sample prediction script
│
├── requirements.txt         # Project dependencies
└── README.md               # Project documentation
```

---

## 🔄 Pipeline Workflow

### 1️⃣ Data Ingestion Step
```python
# steps/ingest_data.py
- Load Ames Housing dataset
- Validate data integrity
- Store raw data
```

### 2️⃣ Data Cleaning Step
```python
# steps/clean_data.py
- Handle missing values
- Remove outliers
- Data type conversions
- Feature validation
```

### 3️⃣ Feature Engineering Step
```python
# steps/feature_engineering.py
- Create derived features
- Encode categorical variables
- Scale numerical features
- Feature selection
```

### 4️⃣ Model Training Step
```python
# steps/train_model.py
- Train Linear Regression model
- Hyperparameter tuning
- Model serialization
- MLflow logging
```

### 5️⃣ Model Evaluation Step
```python
# steps/evaluate_model.py
- Calculate performance metrics
- Generate evaluation reports
- Log metrics to MLflow
- Model comparison
```

---

## 📊 Model Performance

The Linear Regression model trained on the Ames Housing Dataset achieves:

| Metric | Value |
|--------|-------|
| **R² Score** | 0.XX |
| **MSE** | X.XXX |
| **RMSE** | X.XXX |
| **MAE** | X.XXX |

> **Note**: Update these values with your actual model performance metrics from MLflow experiments.

---

## 📚 Documentation

### Understanding the Architecture

- **`src/`**: Contains all source code organized by functionality
- **`pipelines/`**: Orchestrates the workflow by connecting steps
- **`steps/`**: Individual, reusable pipeline components
- **`config.yaml`**: Single source of truth for all configurations

### Key Design Principles

1. **Single Responsibility**: Each module has one clear purpose
2. **DRY (Don't Repeat Yourself)**: Reusable components
3. **Configuration Over Code**: Easy experimentation via YAML
4. **Testability**: Modular design enables easy testing
5. **Scalability**: Easy to add new features or models

### Additional Resources

- [MLflow Documentation](https://mlflow.org/docs/latest/index.html)
- [Ames Housing Dataset](http://jse.amstat.org/v19n3/decock.pdf)
- [Python OOP Best Practices](https://realpython.com/python3-object-oriented-programming/)

---

## 🤝 Contributing

Contributions are welcome! This project is designed to help others learn industry-standard ML workflows.

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Contribution Ideas

- Add new ML algorithms (Random Forest, XGBoost, etc.)
- Implement cross-validation
- Add data visualization dashboards
- Improve documentation
- Add unit tests
- Implement CI/CD pipelines
- Add Docker containerization
- Create REST API for predictions

### Code Style

- Follow PEP 8 guidelines
- Add docstrings to functions and classes
- Write unit tests for new features
- Update documentation as needed

---

## 🗺️ Roadmap

- [x] Basic pipeline structure
- [x] MLflow integration
- [x] Linear Regression model
- [ ] Add multiple ML algorithms
- [ ] Implement cross-validation
- [ ] Add automated testing (pytest)
- [ ] CI/CD with GitHub Actions
- [ ] Docker containerization
- [ ] REST API deployment
- [ ] Streamlit dashboard
- [ ] Comprehensive documentation
- [ ] Feature importance analysis
- [ ] Model interpretability (SHAP)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Vinod Bavage

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 📧 Contact

**Vinod Bavage**

- GitHub: [@vinodbavage31](https://github.com/vinodbavage31)
- Project Link: [MachineLearning-Workflow-System](https://github.com/vinodbavage31/MachineLearning-Workflow-system)

---

<div align="center">

### ⭐ If you found this project helpful, please give it a star!

**Built with ❤️ for the ML community**

---

*This project demonstrates industry-standard ML engineering practices and is open for learning and contribution.*

</div>
