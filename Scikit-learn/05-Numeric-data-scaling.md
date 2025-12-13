📍The Necessity of Scaling:

✔️The requirement for numeric data scaling arises when features used for prediction, typically housed in the X data array, are measured on vastly different numerical scales.

- Impact on Algorithms:

  If one feature, such as "square footage," is measured in the thousands, while another, like "proximity to school," is measured in single-digit miles,
  the axis with the larger numbers will have a much bigger effect on calculations, especially in algorithms that rely on distance, like the K-Nearest Neighbor (KNN) regressor.
  This disproportionate influence can skew the resulting predictions in an undesirable way.
- Rethinking the Model:

  Because scaling is so critical, simply feeding raw data into a model is insufficient, forcing practitioners to rethink what the model is,
  expanding the definition to include pre-processing steps like scaling.

✔️The primary goal of scaling is to ensure that the effect each column has on the prediction is on a level playing field. This transformation makes the data "numerically a bit more stable" by aligning the axes.
<hr>

📍Standard Scaling vs. Quantile Scaling:

1️⃣ Standard Scaling (StandardScaler):

The StandardScaler is presented as a standard way of scaling numeric data.
- Mechanism: For each column, it calculates the mean and the variance. It then standardizes each data point (x) by subtracting the mean and dividing the result by the standard deviation (the square root of the variance).
- Result: This process produces data that revolves around zero, with its variance "kept at bay".
- Weakness (Outliers): A major drawback of the StandardScaler is its sensitivity to outliers. Since the mean and standard deviation are heavily influenced by extreme values, scaling using this method may not sufficiently mitigate the impact of outliers on subsequent algorithms.

2️⃣ Quantile Scaling (QuantileTransformer):

The QuantileTransformer is introduced as an alternative, more robust pre-processing step, particularly when outliers are present.
- Mechanism: Instead of using the mean and standard deviation, this method uses quantiles (percentiles). For example, the 50th percentile is the point where 50% of the data lies on either side.
- Robustness: By using quantiles instead of means, the resulting scaled representation ensures that the distance from an outlier to the 75th quantile is "a lot smaller" than it would be under standard scaling. This technique is inherently less influenced by outliers.
- Result: The sources demonstrate that applying the QuantileTransformer can result in the minimum and maximum values on both axes being precisely equal to zero and one, and it produces a very different output compared to the StandardScaler.
Scaling within Feature Engineering and Pipelines
