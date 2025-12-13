📍Defining the 'Model' as a Pipeline:

The need to integrate pre-processing steps requires an expanded definition of the "model". 
If pre-processing steps—like scaling—have a significant effect on the model's behavior and performance, 
then everything inside the entire system should be regarded as the model.

✔️In scikit-learn, this expanded definition is implemented through the concept of a Pipeline:
1. Pipeline Structure:

   A pipeline chains processing steps (like scaling) and the final estimator (like KNN) together.
2. API Consistency:
  
   The key advantage of treating the entire process as a pipeline is that it maintains the standard scikit-learn API:
   you can call `.fit` on the entire pipeline and `.predict` once it's trained, just like a single estimator.
4. Automatic Learning:

   This structure is particularly useful because pre-processing steps, such as a StandardScaler,
   often need to learn parameters (like the mean and variance for each column) from the data.
   By putting everything into a pipeline, this "learning" aspect of the pre-processing step is handled automatically.

