# Neural Network Charity Analysis

## Overview

Using machine learning and neural networks, the purpose of this analysis was to use the features in a given dataset to help create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. The dataset is a .csv file containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. For this analysis, TensorFlow in Python was used. 

Features include the following:  
* EIN and NAME—Identification columns
* APPLICATION_TYPE—Alphabet Soup application type
* AFFILIATION—Affiliated sector of industry
* CLASSIFICATION—Government organization classification
* USE_CASE—Use case for funding
* ORGANIZATION—Organization type
* STATUS—Active status
* INCOME_AMT—Income classification
* SPECIAL_CONSIDERATIONS—Special consideration for application
* ASK_AMT—Funding amount requested
* IS_SUCCESSFUL—Was the money used effectively

## Results

### Data Preprocessing
* What variable(s) are considered the target(s) for your model? What variable(s) are considered to be the features for your model?

  * IS_SUCCESSFUL column was the target variable. Other 43 variables were features.
 
* What variable(s) are neither targets nor features, and should be removed from the input data?
  * EIN and NAME columns were removed because they had no value. APPLICATION_TYPE was binned and categorized so any unique values with less that 500 records werre marked "Other."

### Compiling, Training, and Evaluating the Model

* How many neurons, layers, and activation functions did you select for your neural network model, and why?
  * The first model had 5,981 parameters with 43 inputs with 2 hidden layers and 1 output layer. The first hidden layer had 43 inputs, 80 neurons, and 80 bias terms. The second hidden layer had 80 inputs (number of neurons from first hidden layer), 30 neurons, and 30 bias terms. Output layer had 30 inputs, 1 neuron, and 1 bias term. RELU function was used to activate hidden layers. Sigmoid function was used to activate output layer. 

* Were you able to achieve the target model performance?
  * The target model performance was 75%, which was never reached by the model. 
  
* What steps did you take to try and increase model performance?
  * Optimization 1 increased neurons for hidden layer 1 to 95 and hidden layer 2 to 45, removed special_considerations_y, and income_amount and ask_amount were binned. Accuracy was 72.3%. Optimization 2 increased neurons for hidden layer 1 to 95 and hidden layer 2 to 45, removed special_considerations_y, and binned income_amount and affiliation. Accuracy was 72.5%. Optimization 3 increased neurons for hidden layer 1 to 180 and hidden layer 2 to 90, removed special_considerations_y, and binned income and affiliation. Accuracy was 72.5%.
 
 Optimization 1
 ```
 268/268 - 0s - loss: 0.5672 - accuracy: 0.7230 - 306ms/epoch - 1ms/step
Loss: 0.5672414898872375, Accuracy: 0.7230320572853088
 ```
 
 Optimization 2
 
 ```
268/268 - 1s - loss: 0.5645 - accuracy: 0.7250 - 539ms/epoch - 2ms/step
Loss: 0.5645004510879517, Accuracy: 0.7250145673751831
 ```
 
 Optimization 3
 
 ```
 268/268 - 0s - loss: 0.5785 - accuracy: 0.7250 - 421ms/epoch - 2ms/step
Loss: 0.5785265564918518, Accuracy: 0.7250145673751831
 ```

## Summary

In summary, none of the model variations reached 75% accuracy or greater. Removing variables and  increasing or decreasing the neurons did not help increase the accuracy. Because neural networks are so complex, you could try and set up a function that tries different iterations and variations of the feature parameters.
