# Analysis
## Overview of Project
Alphabet Soup, a nonprofit philanthropic foundation, is dedicated to helping organizations that protect the environment, improving people's well-being, and uniting the world. The company's goal is to analyze the impact of each donation and vet potential recipients in order to ensure the foundation's money is being used effectively. A deep learning model was employed trained by historical donation data and served as a binary classifier that predicts whether the organization will benefit from Alphabet Soup's funding. 

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
   * INCOME_AMT - Income classification
   * SPECIAL_CONSIDERATIONS - Special consideration for application (removed during Optimization)
   * ASK_AMT - Funding amount requested
 * Variables that are neither targets nor features and were removed from the input data:
   * EIN and NAME - Identification columns
   * SPECIAL_CONSIDERATIONS (removed during Optimization)
  
Compiling, Training, and Evaluating the Model

![1](https://user-images.githubusercontent.com/57520471/179378680-84db02fb-e87a-4ac1-8c47-609224e866a3.png)
![original_model](https://user-images.githubusercontent.com/57520471/179378686-f6097121-e237-49a6-8b61-26008a63784c.png)

  * The base model had 2 hidden layers, 80 neurons for first layer, and 30 neurons for the second. Both hidden layers had ReLU activation functions, and the outer layer had Sigmoid activation. Sigmoid is best for binary classification problems such as this one. Also, ReLU activation is best for nonlinear data. This model yielded a 70.0% accuracy rate.

![opt_1](https://user-images.githubusercontent.com/57520471/179378835-ea2a81e3-8483-4872-9768-19e26985a763.png)
![opt_1 1](https://user-images.githubusercontent.com/57520471/179378832-edba59f0-2011-4072-baf8-16119b53afe2.png)

  * The target accuracy rate is 75% so the first attempt to increase accuracy by removing columns and reducing classification amounts. The column 'SPECIAL_CONSIDERATIONS' was dropped in addition to 'EIN' and 'NAME'. This caused the accuracy rate to decrease to 53.6%.

![opt_2](https://user-images.githubusercontent.com/57520471/179379147-51212101-37df-46c3-a81a-0e9a0222ec78.png)
![opt_2 1](https://user-images.githubusercontent.com/57520471/179379146-1aa7510e-1e50-4b10-be1d-04e88b37adec.png)
 
  * In the second attempt at increasing the accuracy rate, a hidden layer and additional neurons were added. The three hidden layers had 100, 50, 4 neurons and all had ReLU activation. This model yielded a similar result to previous model with an accuracy rate of 53.9%. 
 
![opt_3](https://user-images.githubusercontent.com/57520471/179379156-429ef46f-bcb8-4f25-be22-64e053e9c831.png)
![opt_3 1](https://user-images.githubusercontent.com/57520471/179379155-14c18b56-096d-4eb4-b1ba-416516cefb59.png)

  * In the last attempt, the activation function of the hidden layers from the second attempt model was changed. The model utilized Tanh activation instead of ReLU in the hidden layers and yielded a 42.8% accuracy rate. 
  
## Summary 
Overall, the result of the deep learning model was unsuccessful at producing over a 75% accuracy rate. The model after optimization ended with an accuracy rate of 42.8% compared to initial model with 70.0%. The changes demonstrated include reducing columns, decreasing classification value counts, adding hidden layers, adding neurons, and changing the activation function used. The decrease in accuracy with these changes means the model might be overfitted. To prevent overfitting, I would recommend using Random Forest classifiers. Random Forest classifiers are robust against overfitting and runs efficiently on large datasets with better accuracy.
