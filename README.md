# Deep-Learning-Challenge

## Background
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years.

## Neural Network Model Report

### Overview
The purpose of this analysis was to create a model that could predict whether applicants will be successful after receiving funding from Alphabet Soup. There was an initial pass at creating a model, and then that model was analyzed to determine its level of accuracy. After that, several techniques were used to try and optimize this model, with the goal of acheiving at least an accuracy of 75%

### Results

- Data Processing
  - I removed the 'EIN' and 'NAME' variables as they were not necessary for the initial model as they were neither targets nor features.
  - All remaining variables besides the 'IS_SUCCESSFUL' variable were the features for this model. 
  - The target variable for this model is the 'IS_SUCCESSFUL' variable which displays whether an applicant was successful or not. Ultimately we want to predict this variable.
 
- Compiling, Training, and Evaluating the Model
  - For the first model, I used 3 layers. The first two used relu activation functions while the final layer was a sigmoid activation function. I used 80 neurons for the first layer, 30 for the second, and finally 1 nueron for the final layer. I felt this approach would give enough complexity to build a decent model.
  - The initial model slightly underperformed with an accuracy of 72.80% so I needed to take a few steps to try and improve accuracy.
  - First I wanted to try running an auto optimization to see if there was a better model for the data. While this slightly improved the model, I still didn't achieve the target accuracy. I then had to manipulate the original dataset slightly to help improve the model. I first used a lower cutoff value for both the CLASSIFICATION and APPLICATION_TYPE variables. Then I decided to keep in the NAME variable, and I binned the NAME and ASK_AMT variables to reduce the number of rare values. After doing this and re-running the auto-optimization function, I was able to achieve the desired accuracy of at least 75%.
 
### Summary
Overall I was able to achieve the desired output of 75% accuracy. While this is a decent score, there still could be other steps to improve the accuracy. As I saw with the NAME variable, adding in and binning additional variable could be helpful. Also, I ran this model with a lower number of epochs (20) than in the initial model (100). Increasing this number could help performance as well, but I would recommended testing it on the model itself instead of increasing the number of epochs in the auot-optimization as this will lead to a very lengthy runtime for the auto-optimization. 
