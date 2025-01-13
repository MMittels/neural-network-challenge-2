# Neural Network Challenge 2

## Project Description
<p>ABC Company is concerned about employee attrition and you were asked to create a neural network that Human Resources can use to predict whether employees are likely to leave the company.  Additionally, Human Resources believes that some employees may be better suited to other departments, so you were also asked to predict the department that best fits each employee.</p>

## Preprocessing
  - A dataset was provided containing two targets needed for the model - attrition and department.  The csv file was read into the model.
  - 10 features were picked from the provided dataset.  All features were numeric so no encoding was needed but a StandardScaler was used.
  - train_test_split was used to set up features (X) and targets (y)
  - Both targets needed to be encoded with One Hot Encoder to complete preprocessing

## Create, Compile, and Train Model
   - First, an input layer was set up based on the number of features (len(X_train_scaled[0]))
   - Second, two shared layers were created
   - Then branches were created with a hidden layer and output layer for the attrition and department targets
   - The model was then created, compiled, and summarized
   - The model was then trained with 100 epochs, batches of 35 with a validation split of 0.20
   - The model was evaluated based on accuracy

## Summary

Based on the results from the model, the following questions were explored:
   - Is accuracy the best metric to use on this data? Why or why not?
      - Accuracy may not be the best metric on this data as both the attrition and department targets are unbalanced. 
         - Since attrition is binary, AUC-ROC may be a better measure. Precision could also be used as a measurement for attrition since we are trying to predict if employees will leave the company. 
         - For understanding if employees may be better suited for a different department recall may be a better measurement as it measures the ability of the model to find the relevant cases (true positives).

What activation functions did you choose for your output layers, and why?
   - For the attrition output layer, the 'sigmoid' activation function was used beacause the attrition target was binary and I wanted a binary out, which would be achieved through the 'sigmoid' function. 'Softmax' activation function was used for department because there were three targets associated with department and the output was mutually exclusive - making 'softmax' the optimal activiation function for department.

Can you name a few ways that this model might be improved?

   - The model might be improved by adding more layers, more neurons, or more epochs. Additionally, adding more data (if possible) could be helpful in improving model performance.