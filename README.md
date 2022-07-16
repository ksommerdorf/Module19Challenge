# Analysis
## Overview of Project

## Results
Data Processing
 * The target for this model: IS_SUCCESSFUL which provides if the money used effectively with a value of '1' for yes and '0' for no. 
 * The features of this model: 
   * APPLICATION_TYPE - Alphabet Soup application type
   * AFFILIATION - Affiliated sector of industry
   * CLASSIFICATION - Government organization classification
   * USE_CASE - Use case for funding
   * ORGANIZATION - Organization type
   * STATUS - Active status
   * INCOME_AMT - Funding amount requested
   * SPECIAL_CONSIDERATIONS - Special consideration for application (removed during Optimization)
   * ASK_AMT - Funding amount requested
 * Variables that are neither targets nor features and were removed from the input data:
   * EIN and NAME - Identification columns
   * SPECIAL_CONSIDERATIONS (removed during Optimization)
  
Compiling, Training, and Evaluating the Model
  * The base model had 2 hidden layers, 80 neurons for first layer, and 30 neurons for the second. Both of the hidden layers had ReLU activation functions and the outer layer had Sigmoid activation. Sigmoid is best for binary classificiation problems such as this one. Also ReLU activation is best for nonlinear data. This model yielded a 70.0% accuracy rate.
  * The target accuracy rate is 75% so I first attempted to increase accuracy by removing columns and reducing classification amounts. The column 'SPECIAL_CONSIDERATIONS' was dropped in addition to 'EIN' and 'NAME'. This caused the accuracy rate to decrease to 53.6%. 
  * In the second attempt at increasing the accuracy rate, a hidden layer and additional neurons were added. The three hidden layers had 100, 50, 4 neurons and all had ReLU activation. This model yielded a similar result to previous model with an accuracy rate of 53.9%. 
  * In the last attempt, the activation function of the hidden layers from the second attempt model was changed. The model utilized Tanh activation instead of ReLU in the hidden layers and yielded a 42.8% accuracy rate. 
  
## Summary 

Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation. 
