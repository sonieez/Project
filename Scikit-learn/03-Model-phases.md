📍Model Phases in Scikit-learn:

1️⃣Phase 1: Creation 

  When a model is created as a Python object, it has not yet seen any data and cannot make predictions.

2️⃣Phase 2: Learning/Training (The `.fit` Step) 

This phase is where the model is trained or learns from the data. In Scikit-learn terminology, this is called the `.fit` step.

3️⃣Phase 3: The Prediction (The `.predict` API)

Once the model has been fitted using the `.fit` method, it is ready to make predictions using the `.predict` method. 
This is where the trained model uses the learned patterns to estimate outcomes for new or existing data.
<hr>

📍Core Concept: Consistency of the API

One of the most valuable core concepts of Scikit-learn is the consistent API—specifically, 
the universal application of the `.fit` and `.predict` methods:

✔️ Model Agnosticism: 

Whether a user is employing a K-Nearest Neighbors Regressor or a Linear Regression model, the interaction sequence remains exactly the same: `.fit` followed by `.predict`.

✔️ Composability: 

This consistent API is maintained even as the definition of a "model" evolves:    
  
  ◦ Simple Estimators: 
  
  Basic machine learning algorithms adhere to `.fit` and `.predict`.
  
  ◦ Pipelines: 
  
  When pre-processing steps are added into a single Pipeline object, the entire pipeline still exposes the `.fit` and `.predict` API, simplifying the interface even when multiple chained steps are involved. 
  
  ◦ Meta Estimators: 
  
  Sophisticated objects that manage methodology, like GridSearchCV (which handles cross-validation and hyperparameter search), 
  also have a `.fit` as well as a `.predict` method attached, reinforcing the modularity of the system.
