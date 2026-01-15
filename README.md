# 🔥 Forest Fire Predictor - ML Model

A machine learning web application that predicts forest fire intensity using the Algerian Forest Fires dataset. Built with Flask and scikit-learn, featuring Ridge Regression for accurate predictions.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Model Details](#model-details)
- [Technologies Used](#technologies-used)
- [Deployment](#deployment)
- [License](#license)

## 🌟 Overview

This project implements a machine learning model to predict the Fire Weather Index (FWI) based on various meteorological and environmental factors. The model is deployed as a Flask web application with a user-friendly interface for real-time predictions.

## ✨ Features

- **Machine Learning Model**: Ridge Regression model trained on Algerian Forest Fires dataset
- **Web Interface**: Interactive Flask-based web application
- **Real-time Predictions**: Instant predictions based on input parameters
- **Data Preprocessing**: Standardized feature scaling for improved accuracy
- **Comprehensive Analysis**: Includes EDA and feature engineering notebooks

## 📊 Dataset

The project uses the **Algerian Forest Fires Dataset** containing meteorological data from two regions of Algeria (Bejaia and Sidi Bel-abbes) during the summer period (June to September) of 2012. 

### Input Features:
- **Temperature**: Temperature in Celsius degrees (22 to 42)
- **RH**: Relative Humidity in % (21 to 90)
- **Ws**: Wind speed in km/h (6 to 29)
- **Rain**: Total day in mm (0 to 16. 8)
- **FFMC**: Fine Fuel Moisture Code index
- **DMC**: Duff Moisture Code index
- **ISI**: Initial Spread Index
- **Classes**:  Fire/Not Fire classification
- **Region**: Geographical region (0 or 1)

### Output: 
- **FWI**: Fire Weather Index prediction

## 📁 Project Structure

```
TestForestFire-ML-Model/
├── . ebextensions/
│   └── python.config          # AWS Elastic Beanstalk configuration
├── models/
│   ├── ridge.pkl              # Trained Ridge Regression model
│   └── scaler.pkl             # StandardScaler for feature preprocessing
├── Notebooks/
│   ├── 2.0-EDA And FE Algerian Forest Fires.ipynb
│   ├── 3.0-Model Training.ipynb
│   ├── Algerian_forest_fires_cleaned_dataset.csv
│   └── Algerian_forest_fires_dataset_UPDATE. csv
├── templates/
│   ├── home.html              # Prediction page
│   └── index.html             # Landing page
├── application.py             # Flask application
├── requirements.txt           # Python dependencies
├── . gitignore
└── LICENSE                    # Apache License 2.0
```

## 🚀 Installation

### Prerequisites
- Python 3.7+
- pip package manager

### Setup Steps

1. **Clone the repository**
```bash
git clone https://github.com/TheKunal21/TestForestFire-ML-Model.git
cd TestForestFire-ML-Model
```

2. **Create a virtual environment** (recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

## 💻 Usage

### Running Locally

1. **Start the Flask application**
```bash
python application.py
```

2. **Access the application**
   - Open your web browser and navigate to `http://localhost:5000`
   - Or `http://127.0.0.1:5000`

3. **Make predictions**
   - Navigate to the prediction page
   - Enter the required meteorological parameters
   - Click submit to get the FWI prediction

### API Endpoint

**POST** `/predictdata`

Input form data:
- Temperature (float)
- RH (float)
- Ws (float)
- Rain (float)
- FFMC (float)
- DMC (float)
- ISI (float)
- Classes (float)
- Region (float)

Response:  Predicted FWI value

## 🧠 Model Details

### Algorithm: Ridge Regression
- **Type**: Linear regression with L2 regularization
- **Purpose**: Prevents overfitting and handles multicollinearity
- **Preprocessing**: StandardScaler for feature normalization

### Model Pipeline:
1. Data collection and cleaning
2. Exploratory Data Analysis (EDA)
3. Feature Engineering
4. Model training with Ridge Regression
5. Model evaluation and optimization
6. Serialization (pickle) for deployment

### Notebooks:
- `2.0-EDA And FE Algerian Forest Fires. ipynb`: Data exploration and feature engineering
- `3.0-Model Training.ipynb`: Model selection, training, and evaluation

## 🛠️ Technologies Used

- **Backend**: Flask (Python web framework)
- **Machine Learning**: scikit-learn
- **Data Processing**: pandas, numpy
- **Visualization**: seaborn, matplotlib
- **Deployment**: gunicorn, AWS Elastic Beanstalk
- **Model Serialization**: pickle

## 🌐 Deployment

This application is configured for deployment on **AWS Elastic Beanstalk** using the configuration in `.ebextensions/python.config`.

### Deployment Steps:
1. Install AWS EB CLI
2. Initialize EB application
3. Deploy using `eb deploy`

The application uses `gunicorn` as the WSGI server for production deployment.

## 📝 License

This project is licensed under the **Apache License 2.0** - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Kunal Saini** ([@TheKunal21](https://github.com/TheKunal21))

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! 

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## ⭐ Show your support

Give a ⭐️ if this project helped you! 

---

**Note**: This is a demonstration project for educational purposes. For production use in critical fire prediction systems, additional validation and testing would be required. 
```
