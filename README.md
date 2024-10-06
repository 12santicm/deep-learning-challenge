# deep-learning

## Overview of the Analysis

The purpose of this analysis is to evaluate the factors contributing to the success of non-profit organizations in obtaining funding. With a vast amount of data collected from various organizations, the goal is to determine which features are most indicative of a successful funding outcome and to build a predictive model that can help identify successful applications.

## Results

**Data preprocessing:**

 * Variable target: ``IS_SUCCESSFUL``
   This variable indicates whether a funding application was successful (1) or not (0). It serves as the binary classification target variable for the model.

 * Variable feature: 
  - ``APPLICATION_TYPE``: Type of application submitted by the non-profit organization.
  - ``CLASSIFICATION``: Internal classification of the non-profit.
  - ``STATUS``: Current status of the application.
  - ``INCOME_AMT``: Income amount category of the organization.
  - ``ASK_AMT``: Amount of funding requested by the organization.

 * Unnecessary variables:
  - ``EIN`` and ``NAME``: Identification columns 

**Compiling, Training, and Evaluating the Model**

  Number of Layers:

  * The final model uses a 4-layers, which includes:

     Input Layer
     Three Hidden Layers
     Output Layer

  * Number of Neurons:

     Layer 1: 100 neurons
     Layer 2: 50 neurons
     Layer 3: 20 neurons
     Output Layer: 1 neuron (for binary classification)


  * Activation Functions:

     The hidden layers use the ReLU (Rectified Linear Unit) activation function.
     Reason: ReLU is commonly used for hidden layers because it helps mitigate the vanishing gradient problem, allows for  faster computation, and provides good performance in deep neural networks.

     Output Layer: The output layer uses the Sigmoid activation function.
     Reason: Sigmoid is ideal for binary classification problems, as it outputs a probability value between 0 and 1, which can be interpreted as the likelihood of a successful funding application.

  * This configuration:

     The chosen number of neurons and layers allows the model to learn complex patterns in the data without overfitting.
     Using ReLU activation functions in the hidden layers allows the model to learn efficiently without suffering from the vanishing gradient problem.


   * Attempts to improved the model performance:

   1. For the first attempt to improve the original model (Started_Code.ipynb, accuracy: 0.72434401512146), one more layer was added, resulting in:

     - 80 - 100
     - 30 - 50
     - 20

     More epochs were added:
     -  3 - 10

     *Result*: The result of this model was an accuracy of 0.7284256815910339

   2. For the second attempt to improve the model, more layers were added, resulting in:

   
     - 100 - 150
     - 50 - 100
     - 50
     - 20

     More epochs were added:
     -  10 - 30

     *Result*: The result of this model was an accuracy of 0.7276967763900757

   3. For the last attempt to improve the model, the activation funtion was changed, as well as changing the classification and application number of bins:


     - New activation function ``tanh``

     - Changed of bins
        Classification from 1800 to 2000
        Application fron 500 to 1000

      *Result*: The result of this model was an accuracy of 0.7258017659187317   

## Summary: 

- The final deep learning model achieved an accuracy of approximately 72.8% in predicting the success of non-profit organization funding applications.

- While this accuracy is a reasonable starting point, it falls slightly short of the target accuracy of 75%. The model's performance indicates that it captures a good portion of the relationships between features and the target variable

**Recommendation:**

- Given the nature of this classification problem and the complexity of the dataset, a different machine learning model such as Random Forest might provide better results. This model is well-suited for structured/tabular data and can handle a large number of features with various importance levels more effectively.