# Linear Regression Model Deployment on AWS

## Overview
This project demonstrates the deployment of a Linear Regression model using the Algerian Forest Fires dataset. The model is built using Ridge Regression and deployed as a Flask application. The deployment is configured for AWS using Elastic Beanstalk and CodePipeline by connecting to GitHub.

## Project Structure
```
linear_reg_aws_deployment/
│-- dataset/                 # Contains the Algerian Forest Fires dataset
│-- models/                  # Stores trained Ridge Regression model and Standard Scaler (pickle files)
│-- notebooks/               # Jupyter Notebooks for data exploration and model training
│-- templates/               # HTML files for index and home pages
│-- .ebextensions/           # AWS Elastic Beanstalk configuration files
│-- app.py                   # Flask application for model inference
│-- requirements.txt         # Dependencies
│-- README.md                # Project documentation
```

## Requirements
- Python 3.x
- Flask
- Scikit-learn
- NumPy
- Pandas
- AWS CLI (for deployment)
- Elastic Beanstalk CLI

## Setup and Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/Koushik7893/linear_reg_aws_deployment.git
   cd linear_reg_aws_deployment
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate   # For MacOS/Linux
   venv\Scripts\activate      # For Windows
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Model Training
1. **Data Preprocessing and Model Training:**
   - Jupyter Notebooks in the `notebooks/` directory contain data analysis and model training.
   - The trained Ridge Regression model is saved in the `models/` folder as `ridge.pkl`.
   - The StandardScaler used for feature scaling is also stored as `scaler.pkl`.

## Running the Flask Application
1. **Start the Flask server:**
   ```bash
   python app.py
   ```
2. **Access the application:**
   - Open a web browser and navigate to `http://127.0.0.1:5000/`
   - Enter input values and get predictions.

## API Endpoints
- **Home Page:** `GET /`
- **Prediction:** `POST /predictdata`
  - **Input Parameters:**
    - Temperature, RH (Relative Humidity), Wind Speed (Ws), Rain, FFMC, DMC, ISI, Classes, Region
  - **Response:** Predicted fire risk value

## AWS Deployment
All AWS deployment steps will be handled through the AWS Console using Elastic Beanstalk and CodePipeline, connecting directly to GitHub. All deployment files will be stored in GitHub, and updates will be automatically reflected through CodePipeline.

## Testing Deployment
After deployment, test the application by accessing the AWS Elastic Beanstalk endpoint provided.
