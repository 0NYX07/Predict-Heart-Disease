# ❤️ Heart Disease Prediction Using Machine Learning

**A machine learning web application built with Python, Scikit-learn, Pandas, Joblib, and Streamlit to predict heart disease risk from user-provided medical data.**

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

## 📌 Overview

**Heart Disease Prediction** is a machine learning project that uses a trained Logistic Regression classification model to predict the likelihood of heart disease based on medical parameters provided by the user.

The application provides an interactive interface where users can enter health-related information, including age, sex, chest pain type, resting blood pressure, cholesterol, maximum heart rate, and other clinical attributes.

The application processes these inputs into the feature format expected by the trained model and displays a prediction through a Streamlit web interface.

The machine learning model is trained using a given dataset containing medical features and corresponding target labels. The trained model is saved and reused to generate predictions for new inputs.

**Repository:** [0NYX07/Predict-Heart-Disease](https://github.com/0NYX07/Predict-Heart-Disease)

## 🎯 Project Objectives

- Apply supervised machine learning to a healthcare-related classification problem.
- Train and use a Logistic Regression model.
- Process numerical and categorical medical features.
- Save and load trained machine learning artifacts.
- Build an interactive web application using Streamlit.
- Generate predictions from user-provided medical data.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and feature preparation |
| Scikit-learn | Machine learning and classification |
| Logistic Regression | Prediction model |
| Joblib | Model serialization and loading |
| Streamlit | Interactive web interface |
| Git and GitHub | Version control and repository hosting |

## 🧠 How Machine Learning Is Used

The application follows a supervised machine learning workflow.

### 1. Dataset

A given dataset containing medical attributes is used to train the classification model. Each training record contains input features and a target label indicating the corresponding outcome.

The features used by the web application include:

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG
- Maximum Heart Rate
- Exercise-Induced Angina
- Oldpeak
- ST Slope

### 2. Data Preprocessing

The dataset must be prepared before training. This can include handling missing values, encoding categorical variables, and separating the input features from the target column.

Categorical features are represented using encoded numerical columns so that the model can process them.

### 3. Model Training

The project uses **Logistic Regression**, a supervised learning algorithm commonly used for binary classification.

During training, the model learns relationships between the input features and target labels. It can then use these learned relationships to predict the class of new records.

### 4. Model Saving

The trained model and supporting information are stored in serialized files using Joblib.

- `LogisticRegression.pkl` stores the trained classification model.
- `columns.pkl` stores the expected feature column names.
- `scaler.pkl` stores a fitted feature scaler from the training workflow.

These files allow the application to reuse previously created artifacts instead of retraining the model every time it starts.

### 5. Prediction

When the user clicks **Predict**, the application:

1. Collects the medical parameters entered in the interface.
2. Constructs a dictionary containing the feature values.
3. Converts the dictionary into a Pandas DataFrame.
4. Adds missing expected columns with zero values.
5. Reorders the features to match the saved column list.
6. Passes the prepared DataFrame to the trained model.
7. Displays the predicted class.

The current version of `app.py` calls `model.predict(input_df)` directly, without applying `scaler.pkl`.

For reliable predictions, preprocessing during inference must match the preprocessing used during model training.

## 📂 Project Structure

```text
Predict-Heart-Disease/
│
├── app.py
├── LogisticRegression.pkl
├── scaler.pkl
├── columns.pkl
├── README.md
└── .venv/
```

| File | Description |
|---|---|
| `app.py` | Streamlit interface and prediction logic |
| `LogisticRegression.pkl` | Saved Logistic Regression model |
| `scaler.pkl` | Saved feature scaler |
| `columns.pkl` | Expected model input feature columns |
| `README.md` | Project documentation |
| `.venv/` | Isolated Python environment |

The dataset and model training script are not present in the directory structure shown above.

## ⚙️ Installation and Setup

### Prerequisites

- Python
- pip
- Git
- The saved model artifact files included in the project

### 1. Clone the Repository

```bash
git clone https://github.com/0NYX07/Predict-Heart-Disease.git
cd Predict-Heart-Disease
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate the environment on Linux:

```bash
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
python -m pip install streamlit pandas scikit-learn joblib
```

### 4. Run the Application

```bash
streamlit run app.py
```

Open the local URL displayed in the terminal. By default, Streamlit typically uses:

`http://localhost:8501`

## 🖥️ How to Use

1. Start the application.
2. Enter the patient's age.
3. Select sex and chest pain type.
4. Enter resting blood pressure and cholesterol.
5. Select fasting blood sugar and resting ECG.
6. Enter maximum heart rate and exercise-induced angina.
7. Select Oldpeak and ST Slope.
8. Click **Predict**.
9. View the model's predicted result.

## 🔬 Key Machine Learning Concepts

- **Supervised Learning:** Learning patterns from labeled training data.
- **Binary Classification:** Predicting one of two target classes.
- **Logistic Regression:** A classification algorithm that estimates class probabilities.
- **Categorical Encoding:** Converting categorical variables into numerical features.
- **Feature Alignment:** Ensuring input columns match the model's expected features.
- **Model Serialization:** Saving and loading trained model artifacts.
- **Inference:** Generating predictions from new input data.
- **Streamlit Deployment:** Providing a user interface for interacting with a trained model.

## ⚠️ Limitations and Considerations

- Prediction quality depends on the dataset, training procedure, and model evaluation.
- The feature encoding and column order must match the training pipeline.
- The current application does not use the saved scaler during prediction. Confirm whether scaling was used during training before deciding whether to remove or apply it.
- The interpretation of classes `0` and `1` must match the target-label encoding used during training.
- Model performance should be assessed using metrics such as precision, recall, F1-score, and a confusion matrix.
- Serialized model files should only be loaded from trusted sources.

**Medical disclaimer:** This project is intended for educational and demonstration purposes only. It is not a clinically validated diagnostic tool and must not be used to make medical decisions.

## 🚀 Future Enhancements

- Display prediction probabilities.
- Add model evaluation metrics and visualizations.
- Improve input validation and error handling.
- Include the dataset source and model training notebook.
- Add a prediction history feature.
- Improve interface design and accessibility.
- Deploy the application online.
- Evaluate false negatives and other clinically relevant performance measures.

## 👨‍💻 Author

**Krishna Sahni**

- GitHub: [@0NYX07](https://github.com/0NYX07)
- Project Repository: [Predict-Heart-Disease](https://github.com/0NYX07/Predict-Heart-Disease)

---

*Developed as a machine learning project to explore supervised classification and interactive web application development using Python.*
