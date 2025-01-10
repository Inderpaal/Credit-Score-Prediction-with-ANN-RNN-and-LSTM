# Credit Score Prediction with ANN, RNN, and LSTM

This project focuses on building and evaluating Artificial Neural Networks (ANN), Recurrent Neural Networks (RNN), and Long Short-Term Memory (LSTM) models to forecast credit scores based on key features in the dataset.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Features and Preprocessing](#features-and-preprocessing)
- [Model Architectures](#model-architectures)
- [Results and Evaluation](#results-and-evaluation)
- [Usage](#usage)
- [Future Enhancements](#future-enhancements)


---

## Introduction

Predicting credit scores is a critical task for financial institutions to assess customer creditworthiness. This project explores three neural network architectures — ANN, RNN, and LSTM — to accurately predict credit scores using a feature-rich dataset.

---

## Dataset Overview

The dataset consists of the following columns:

| Column Name          | Description                                           |
|----------------------|-------------------------------------------------------|
| `RowNumber`          | Index of the row in the dataset                       |
| `CustomerId`         | Unique identifier for the customer                    |
| `Surname`            | Customer's surname                                    |
| `CreditScore`        | Credit score of the customer                          |
| `Gender`             | Gender of the customer (`Male` or `Female`)           |
| `Tenure`             | Number of years the customer has been with the bank   |
| `Age`                | Age of the customer                                   |
| `Balance`            | Account balance of the customer                      |
| `NumOfProducts`      | Number of products the customer has purchased         |
| `HasCrCard`          | Whether the customer owns a credit card (`0` or `1`)  |
| `IsActiveMember`     | Whether the customer is an active member (`0` or `1`) |
| `EstimatedSalary`    | Estimated salary of the customer                      |
| `Exited`             | Whether the customer exited the bank (`0` or `1`)     |

---

## Features and Preprocessing

### Features:
- The dataset contains **categorical and numerical features** related to customer financial behavior.

### Preprocessing:
1. **Feature Selection:** Top 5 features selected using the `SelectKBest` method with chi-squared scores.
2. **Encoding:** Categorical features encoded using `LabelEncoder`.
3. **Scaling:** Numerical features scaled using `StandardScaler`.
4. **Reshaping:** Data reshaped for RNN and LSTM models into `(samples, timesteps, features)` format.

---

## Model Architectures

### ANN Models:
- **Small:** 1 hidden layer with 16 neurons.
- **Medium:** 2 hidden layers with 64 neurons each; dropout included to reduce overfitting.
- **Large:** 3 hidden layers with 128 neurons each.

### RNN Models:
- Simple RNN layers stacked with fully connected layers.

### LSTM Models:
- LSTM layers for long-term dependencies, stacked with dense layers.

---

## Results and Evaluation

| Model    | Architecture | Mean Squared Error (MSE) | Mean Absolute Error (MAE) |
|----------|--------------|--------------------------|---------------------------|
| ANN      | Medium       | **Lowest**               | **Lowest**                |
| RNN      | Small        | -                        | -                         |
| LSTM     | Large        | -                        | -                         |

Training and validation losses were plotted to monitor model convergence and overfitting tendencies.

---

## Usage

1. **Preprocess the Data**  
   Use the `preprocessing.py` script to encode, scale, and prepare the dataset for training.

2. **Train Models**  
   Run the `train_model.py` script to train the ANN, RNN, and LSTM models.

3. **Evaluate Results**  
   Use the `evaluate_model.py` script to compare metrics and visualize loss plots.

4. **Visualize Results**  
   Plot loss curves and prediction errors using the `visualize.py` script.

---

## Future Enhancements

- Add support for hyperparameter optimization using tools like Optuna.  
- Implement additional evaluation metrics such as R² and explained variance.  
- Explore transfer learning to achieve faster convergence and better accuracy.



1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/credit-score-prediction.git
