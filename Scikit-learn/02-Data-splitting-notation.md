📍Data Splitting Notation (X and Y):

When working with data for predictive tasks in Scikit-learn, the common practice is to split the dataset 
into two distinct parts using scientific notation: X and Y.

• X (Features or Predictors): 

This dataset represents everything used to make a prediction. 
For example, in a house price prediction scenario, X would contain information about the house, such as square feet and the size of the garden.

• Y (Labels or Targets): 

This dataset contains the prediction that you are interested in making. 
Continuing the house price example, Y would contain the actual house prices.

This X and Y notation originates from scientific articles, and Scikit-learn adheres to it consistently.

<hr>

📍Context within General Flow and Core Concepts:

The X and Y notation is fundamental to Scikit-learn's General Flow, particularly the `.fit` step:
1. Preparation for Learning:

   Once the data is split into X and Y, the General Flow proceeds to the learning/training phase.
2. The `.fit` API:

   During the `.fit` step (e.g., `model.fit(X, Y)`), both the X and Y datasets are passed to the model.
   It is the model's job to learn the underlying pattern so that it can predict Y using X.
4. Consistency:
  
   This segregation of data enables the consistent application of Scikit-learn's central Application Programming Interface (API),
   where the `.fit` method always accepts the features (X) and the labels (Y).
