# Customer Churn Score Prediction Using a Deep Neural Network with TensorFlow

## Practical No. 4

## Title
**Customer Churn Score Prediction Using a Deep Neural Network with TensorFlow**

## Aim
To develop a Deep Learning model using TensorFlow for predicting a continuous customer churn score from the cleaned Telco Customer Churn dataset and to improve model performance using weight initialization, dropout, and early stopping techniques.

---

## Project Overview

Customer churn prediction is an important business problem in telecommunications and subscription-based industries. Instead of producing only a binary Yes/No churn decision, organizations can use a **churn score** to estimate the likelihood that an individual customer may leave.

In this experiment, the cleaned Telco Customer Churn dataset from Practical No. 3 is used to develop a **Deep Neural Network (DNN)** using TensorFlow/Keras for predicting the continuous **Churn Score**.

The experiment includes:

- Data loading and inspection
- Feature and target separation
- Training, validation, and testing data split
- Deep Neural Network design
- Glorot/Xavier weight initialization
- Dropout regularization
- Experimentation with different dropout rates
- Early stopping
- Model checkpointing and best-model restoration
- Regression model evaluation
- Training and validation loss visualization

---

## Dataset

**Dataset:** Telco Customer Churn Dataset  
**Source:** IBM Dataset  
**Domain:** Telecommunications  
**Problem Type:** Regression / Continuous Score Prediction  
**Target Variable:** Churn Score  

The cleaned dataset used in this experiment contains **7,032 records**. After removing the unnecessary index column, the dataset contains customer-related features such as demographic information, service subscriptions, contract details, billing information, charges, churn information, and Customer Lifetime Value (CLTV).

The target variable for this experiment is **Churn Score**.

---

## Dataset Preparation

The following preprocessing steps were performed:

1. Loaded the cleaned Telco Customer Churn dataset.
2. Inspected the dataset structure and data types.
3. Removed the unnecessary `Unnamed: 0` column.
4. Separated the input features and target variable.
5. Removed `Churn Value` and `Churn Label` from the input features to focus on continuous churn-score prediction.
6. Divided the dataset into:
   - Training Set: 80%
   - Temporary Set: 20%
7. Further divided the temporary set into:
   - Validation Set: 10% of the total dataset
   - Test Set: 10% of the total dataset

---

## Deep Neural Network Architecture

The Deep Neural Network was implemented using TensorFlow/Keras.

### Final Model Configuration

| Layer | Configuration |
|---|---|
| Input Layer | Input features |
| Hidden Layer 1 | 64 neurons, ReLU activation, Glorot/Xavier initialization |
| Dropout Layer 1 | Dropout rate = 0.3 |
| Hidden Layer 2 | 32 neurons, ReLU activation, Glorot/Xavier initialization |
| Dropout Layer 2 | Dropout rate = 0.3 |
| Hidden Layer 3 | 16 neurons, ReLU activation, Glorot/Xavier initialization |
| Hidden Layer 4 | 8 neurons, ReLU activation, Glorot/Xavier initialization |
| Output Layer | 1 neuron, Linear activation |

### Training Configuration

- **Framework:** TensorFlow / Keras
- **Optimizer:** Adam
- **Loss Function:** Mean Squared Error (MSE)
- **Batch Size:** 32
- **Maximum Epochs:** 200
- **Weight Initialization:** Glorot/Xavier Uniform
- **Early Stopping Monitor:** Validation Loss
- **Early Stopping Patience:** 10 epochs
- **Best Model Saving:** ModelCheckpoint based on validation loss

---

## Deep Learning Optimization Techniques

### 1. Weight Initialization

Glorot/Xavier Uniform initialization was applied to the hidden layers to support stable learning and improve gradient flow during neural-network training.

### 2. Dropout Regularization

Dropout layers were added after the first two hidden layers to reduce overfitting.

The following dropout rates were experimented with:

- 0.0
- 0.2
- 0.3
- 0.5

The final model was trained with a dropout rate of **0.3**.

### 3. Early Stopping

Early stopping was used to monitor validation loss with a patience of 10 epochs. The model was configured to restore the best weights after training stopped.

**Training Result:**

- Maximum epochs configured: 200
- Total epochs actually trained: 38
- Best epoch: 28
- Best validation loss: 662.2151

The best-performing model was also saved using `ModelCheckpoint` as:

`best_churn_model.keras`

---

## Model Evaluation

The best saved model was evaluated on the unseen test dataset.

### Final Regression Performance

| Metric | Result |
|---|---:|
| MAE | 21.5652 |
| MSE | 681.2843 |
| RMSE | 26.1014 |
| R² Score | -0.4637 |

These results were obtained from the final evaluation of the saved best model on the test dataset.

---

## Performance Visualization

The experiment includes a performance graph for:

### Training Loss vs Validation Loss

The graph compares:

- Training MSE Loss
- Validation MSE Loss
- Training Epochs

This visualization helps analyze the learning behavior of the neural network and observe changes in training and validation performance over time.

---

## Key Experiment Results

| Parameter | Value |
|---|---|
| Problem Type | Regression |
| Target Variable | Churn Score |
| Maximum Training Epochs | 200 |
| Actual Training Epochs | 38 |
| Best Epoch | 28 |
| Dropout Rate in Final Model | 0.3 |
| Optimizer | Adam |
| Loss Function | Mean Squared Error |
| Weight Initialization | Glorot/Xavier Uniform |
| MAE | 21.5652 |
| RMSE | 26.1014 |
| R² Score | -0.4637 |

---

## Libraries Used

The following libraries are required for this project:

- TensorFlow
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

Install the required libraries using:

```bash
pip install -r Requirements.txt
```

---

## Project Files

```text
Deep-Learning-Neural-Networks-Experiment-004/
│
├── Code.ipynb
├── Requirements.txt
├── README.md
├── LICENSE
└── best_churn_model.keras
```

---

## How to Run the Project

1. Clone or download the repository.
2. Install the required libraries:

```bash
pip install -r Requirements.txt
```

3. Open the Jupyter Notebook:

```text
Code.ipynb
```

4. Ensure that the cleaned Telco Customer Churn dataset used in Practical No. 3 is available in the expected location.
5. Run all cells in sequence to reproduce the experiment.

---

## Business Interpretation

A customer churn score can help organizations identify customers who are more likely to leave. By analyzing predicted churn scores, organizations can support data-driven customer-retention strategies.

Possible business applications include:

- Identifying customers with higher predicted churn scores
- Prioritizing customers for retention campaigns
- Providing targeted offers and discounts
- Improving customer support for at-risk customers
- Designing personalized retention strategies

---

## Conclusion

A Deep Neural Network was developed using TensorFlow/Keras to predict continuous customer churn scores. The experiment explored important Deep Learning techniques, including network architecture design, Glorot/Xavier weight initialization, dropout regularization, early stopping, model checkpointing, and regression-based performance evaluation.

The final model completed training after **38 epochs**, with the best validation performance observed at **epoch 28**. The final test evaluation produced an MAE of **21.5652**, RMSE of **26.1014**, and R² score of **-0.4637**.

This experiment demonstrates the complete workflow of developing and evaluating a Deep Learning regression model for customer churn-score prediction.

---

## Author

**Name:** Dhawal Soni  
**Email:** Add your university email here

---

## Academic Information

**Course:** Artificial Intelligence and Machine Learning  
**Practical No.:** 4  
**Experiment:** Customer Churn Score Prediction Using a Deep Neural Network with TensorFlow

---

## Dataset Resource

**Dataset:** Telco Customer Churn Dataset  
**Source:** IBM  
**Domain:** Telecommunications
