![Neural_Networks_SwissCognitive](https://github.com/user-attachments/assets/a76f398a-a8d8-4ef0-af11-0502c21af244)


# Alphabet Soup Deep Learning Model

## Overview of the analysis

This analysis aims to predict the success of Alphabet Soup-funded organizations using deep learning. We'll train a binary classification model on a dataset of over 34,000 organizations, leveraging their metadata.

## Results

### Data Preprocessing

- **Target variable(s) for the model:** The target variable for the model is `IS_SUCCESSFUL`.
- **Feature variable(s) for the model:** The feature variables for the model include `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT`. 
- **Variable(s) removed from the input data:** The `EIN` and `NAME` columns were removed from the input data as they are identification columns and not useful as features or targets.

- **Feature variable** `NAME` has been brought back in the last model.

### Compiling, Training, and Evaluating the Model

- **Neurons, layers, and activation functions selected for the neural network model and rationale:** The model consists of three hidden layers with 80, 30, and 1 neurons, respectively, and ReLU activation functions. The output layer uses a sigmoid activation function for binary classification. The structure was chosen to provide a balance between complexity and the potential for overfitting, while maintaining the ability to learn complex patterns in the data.
This model did not achive desired accuracy of 75%.
The accuracy achived was 72.8%. 

This project involved training four deep learning models. The initial three models were trained on a dataset excluding the EIN and NAME columns, employing varying numbers of neurons, layers, and binning strategies.
* Attempt1: Use same structure but different number of nurons in each layer and increasing the Epoch from 50 t0 100.
   * Accuracy increased very slightly to 72.7%
* Attempt 2: Optimising the structure using the Keras Tuner
  * Allow activation function to choose between relu, sigmoid, tanh
  * sigmoid is still the only option for the final layer
  * Allow number of neurons to vary from 6 to ~75
  * Accuracy increased to 73.5%
*  Attempt 3:
Try using few neurons (< number of features) with sigmoid activation function for non input layer
   * Accuracy decreased to 72.6%

*  A 4th attempt, in a seperate file not included, was made which resulted in a 78.5%

Our **Feature variable(s) for the model:** The feature variables for the model include `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, `NAME` and `ASK_AMT`. and **Target variable(s) for the model:** The target variable for the model is `IS_SUCCESSFUL`. The model consists of three hidden layers with 14, 7, and 1 neurons, respectively, The output layer uses a sigmoid activation function for binary classification and used Relu for other layers.

- **Achievement of the target model performance:** The model achieved the target accuracy of 78.5%. Despite multiple attempts to improve performance through data preprocessing, neural network architecture tuning, and hyperparameter optimization, no significant gains were observed.

- **Steps taken in attempts to increase model performance:** To increase model performance, the following steps were taken:

  - Dropping additional irrelevant columns from the input data.
  - Creating more bins for rare occurrences in columns and adjusting the number of values for each bin.
  - Adding more neurons to a hidden layer.
  - Adding or removing hidden layers.
  - Using different activation functions for the hidden layers.
  - Increasing or decreasing the number of epochs in the training regimen.

### Summary

The deep learning model demonstrated a 78.5% accuracy in predicting the success of Alphabet Soup-funded organizations. This performance was obtained after extensive experimentation with data preprocessing techniques and neural network architectures.
