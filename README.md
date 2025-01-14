# Complete Machine Learning Project with MLOps and CI/CD Pipelines

This repository showcases an end-to-end machine learning project incorporating MLOps principles and CI/CD pipelines for seamless deployment and production readiness.

## Project Overview

This project demonstrates the entire lifecycle of a machine learning application, starting from data ingestion to deploying the model into production. The project focuses on predicting student performance based on various input features like gender, parental education, test preparation, and scores in other subjects. A Flask web app was developed to take input about a student and predict their potential exam score.

---

## Problem Statement

Educational institutions often seek ways to predict and enhance student performance. This project aims to address the following questions:

- Can a student's performance in exams be accurately predicted based on demographic and academic features?
- How can an automated system help institutions or educators identify students who may need additional support?

### Dataset
The dataset used for this project comes from Kaggle: [Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams). 

---

## Key Steps in the Project

### 1. **Data Ingestion and Transformation Pipeline**
- Loaded the dataset, analyzed the data, and handled missing values if any.
- Performed feature engineering, such as encoding categorical variables and normalizing numeric features.
- Split the dataset into training and testing sets.

### 2. **Model Training Pipeline**
- Designed and implemented a machine learning model training pipeline.
- Experimented with various regression algorithms to predict scores, selecting the best-performing model based on metrics such as Mean Absolute Error (MAE) and R-squared.
- Saved the trained model as a serialized file for deployment.

### 3. **Flask Web Application for Model Deployment**
- Built a Flask web application to serve the model.
- The web app allows users to input details about a student, such as gender, parental education, and test preparation status.
- Based on the inputs, the application predicts the student's likely exam score.
- Deployed the web application to AWS Elastic Beanstalk for production use.

### 4. **Production and CI/CD Pipeline**
- Developed a CI/CD pipeline for automating the build, test, and deployment processes using:
  - **Docker**: To containerize the application for consistent deployments.
  - **AWS ECR**: For storing Docker images.
  - **AWS EC2**: To host and run the application in a production environment.
  - **GitHub Actions**: To automate the CI/CD process, enabling seamless integration and deployment.

---

## Tools and Technologies
- **Programming Language**: Python
- **Libraries**: Flask, Scikit-learn, Pandas, NumPy, Matplotlib
- **MLOps Tools**: Docker, AWS (Elastic Beanstalk, ECR, EC2), GitHub Actions
- **Version Control**: Git
- **CI/CD Pipeline**: Docker, AWS, GitHub Actions

---

## Repository Structure

```
complete-ml-project/
├── .ebextensions           # Elastic Beanstalk configuration files
├── .github/workflows       # CI/CD pipeline configurations for GitHub Actions
├── app.py                  # Flask application file
├── setup.py                # Setup file for the application
├── requirements.txt        # Python dependencies
├── data/                   # Data folder
│   ├── data-s.csv          # Dataset used for the project
├── notebook/               # Jupyter notebooks for EDA and training
│   ├── EDA.ipynb           # Exploratory Data Analysis notebook
│   └── train.ipynb         # Model training notebook
├── src/                    # Source code for the project
│   ├── __init__.py         # Init file for source code package
│   ├── logger.py           # Logging utility for the project
│   ├── exception.py        # Custom exception handling
│   ├── utils.py            # Utility functions
│   ├── components/         # Components for pipeline stages
│   │   ├── __init__.py     # Init file for components package
│   │   ├── data_ingestion.py  # Data ingestion scripts
│   │   ├── data_transformation.py # Data transformation scripts
│   │   ├── model_trainer.py      # Model training scripts
│   ├── pipeline/           # Pipelines for the project
│   │   ├── __init__.py     # Init file for pipeline package
│   │   ├── predict_pipeline.py  # Prediction pipeline scripts
├── templates/              # HTML templates for Flask app
│   ├── home.html           # Home page template
│   ├── index.html          # Index page template
├── logs/                   # Log files
│   ├── daily-wise.log      # Daily log file
├── test_app.py             # Test script for the Flask application
├── .gitignore              # Git ignore file
├── README.md               # Readme file
```

---

## How to Use the Flask App
1. Clone the repository:
   ```bash
   git clone https://github.com/HadeelAls618/complete-ml-project.git
   cd complete-ml-project
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Flask application locally:
   ```bash
   python app.py
   ```

4. Access the application in your browser at `http://localhost:8080`.

5. Input the details about the student and get the predicted score.

