### **Neural Network Model Report for Alphabet Soup**

---

#### **Overview of the Analysis**
The goal of this analysis was to create a deep learning model capable of predicting the success of charity funding applications. By leveraging the dataset, we aimed to build a neural network to classify whether a funding request would be successful based on application features.

---

#### **Results**

##### **Data Preprocessing**
- **Target Variable(s):**
  - `IS_SUCCESSFUL`: Indicates whether a funding application was successful (1) or not (0).

- **Feature Variable(s):**
  - All other columns after preprocessing, including one-hot encoded categorical variables like `APPLICATION_TYPE`, `CLASSIFICATION`, and numerical columns like `ASK_AMT`.

- **Removed Variables:**
  - `EIN` and `NAME`: These identifiers do not contribute to the target prediction.

##### **Compiling, Training, and Evaluating the Model**
- **Model Architecture:**
  - **Neurons:**  
    - Attempt 1: Three hidden layers with 100, 80, and 50 neurons.  
    - Attempt 2: Three hidden layers with 128, 64, and 32 neurons.  
    - Attempt 3: Three hidden layers with 150, 100, and 50 neurons.
  - **Activation Functions:**  
    - ReLU was used for all hidden layers to handle non-linear relationships. The output layer used a sigmoid activation for binary classification.

- **Performance Results:**
  - **Attempt 1:** Accuracy: **72.78%**, Loss: **0.5723**  
  - **Attempt 2:** Accuracy: **72.65%**, Loss: **0.5744**  
  - **Attempt 3:** Accuracy: **72.80%**, Loss: **0.6048**  

- **Target Performance:**  
  The target accuracy of 75% was not achieved. The best accuracy obtained was **72.80%**.

- **Steps to Increase Performance:**
  1. Increased the number of neurons in hidden layers.
  2. Added a dropout layer in Attempt 2 to prevent overfitting.
  3. Increased epochs in Attempt 3 and introduced early stopping to improve learning.
  4. Experimented with activation functions like `tanh` (Attempt 2).

---

#### **Summary**
- **Overall Results:**  
  The deep learning model was unable to surpass the target accuracy of 75%, with the best result being 72.80%. This suggests that the current dataset and model architecture may not fully capture the complexities of the classification problem.

- **Recommendation:**  
  A different model, such as **Random Forests** or **Gradient Boosting (e.g., XGBoost)**, could be more suitable for this problem. These models are effective at handling categorical data and imbalanced datasets without requiring heavy preprocessing like one-hot encoding. Additionally, hyperparameter tuning and feature engineering could further improve results.
