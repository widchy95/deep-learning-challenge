# Report: Neural Network Model for Alphabet Soup Charity Success Prediction

## **Overview of the Analysis**
The purpose of this analysis is to design, train, and optimize a deep learning model to predict whether applicants will be successful if funded by Alphabet Soup Charity. The model classifies applications as "successful" or "unsuccessful," which helps the organization allocate its resources efficiently.

---

## **Results**

### **Data Preprocessing**
- **Target Variable(s):**  
  The target variable for the model is `IS_SUCCESSFUL`, which indicates whether an application was successful or not.
  
- **Feature Variable(s):**  
  The features include all remaining columns after encoding, except `IS_SUCCESSFUL`. These are variables such as `APPLICATION_TYPE`, `CLASSIFICATION`, `STATUS`, `INCOME_AMT`, and other one-hot-encoded categorical data.

- **Removed Variable(s):**  
  Columns such as `EIN` and `NAME` were removed because they are neither relevant features nor targets and could add noise to the model.

---

### **Compiling, Training, and Evaluating the Model**

- **Neurons, Layers, and Activation Functions:**  
  - **Attempt 1:**  
    - Neurons: 100, 80, 50 (3 layers).  
    - Activation Functions: ReLU for hidden layers, sigmoid for output.  
    - Reason: A relatively simple architecture to test baseline performance.  
  - **Attempt 2:**  
    - Neurons: 128, 64, 32 (3 layers).  
    - Activation Functions: Tanh in the first layer, ReLU in the subsequent layers.  
    - Additional dropout layers were added to prevent overfitting.  
    - Reason: To add complexity and adjust activation functions to improve generalization.  
  - **Attempt 3:**  
    - Neurons: 150, 100, 50 (3 layers).  
    - Activation Functions: ReLU for all layers, sigmoid for the output.  
    - Reason: Larger architecture with more neurons and early stopping to prevent overfitting.  

- **Model Performance:**  
  None of the attempts achieved the target accuracy of 75%.  
  - **Attempt 1:** Accuracy = 72.78%, Loss = 0.5723  
  - **Attempt 2:** Accuracy = 72.65%, Loss = 0.5744  
  - **Attempt 3:** Accuracy = 72.80%, Loss = 0.6048  

- **Steps Taken to Improve Model Performance:**  
  - Adjusted the number of neurons and hidden layers.  
  - Experimented with different activation functions (ReLU and Tanh).  
  - Added dropout layers to reduce overfitting.  
  - Increased the number of epochs and introduced early stopping.  

---

### **Summary**
The deep learning model achieved a maximum accuracy of **72.80%**, which fell short of the target accuracy of 75%. Despite optimizing neurons, layers, and activation functions, the model performance plateaued. The primary limitation may lie in the nature of the dataset, where features lack sufficient predictive power for the classification task.

### **Recommendation**
To further improve performance, consider the following alternatives:
- **Random Forest or Gradient Boosting Models:**  
  These models excel at handling categorical data and can perform better with smaller datasets by capturing non-linear relationships.
- **Feature Engineering:**  
  Adding or transforming features, such as interaction terms or binning numerical variables more effectively, may improve predictive power.
- **Hyperparameter Tuning:**  
  Grid search or Bayesian optimization could fine-tune the architecture for better performance.

A different model such as Gradient Boosting could outperform the neural network, as it handles structured data more efficiently and is less sensitive to scaling issues.
