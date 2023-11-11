# ML code
  **Reproducing "Rapid Estimation of Activation Energy"**

This project aims to reproduce the findings presented in the article "Rapid estimation of activation energy in heterogeneous catalytic reactions via machine learning(https://doi.org/10.1002/jcc.25567)". The original work employs a data-driven approach to predict the activation energy of chemical reactions, utilizing reaction energy and introducing the reactants,catalysts,surface and products as descriptors.

**Overview**

In my implementation, two machine learning models are employed: a simple Multi-Layer Perceptron (MLP) model and an ensemble learning model (Random Forest). Notably, the original article does not address the issue of outliers in the raw material (DataSet file), which is identified as a crucial aspect of data preprocessing. Approximately 100 outliers were detected and removed from the main dataset using a developed object-oriented class for the Interquartile Range (IQR) outlier detection method.

**Data**

In the __## Assigned Number__ file, the categorical nature of the data is introduced. The numbers are assigned to different chemical compounds, so the model can understand the changings on the reaction's nature. In the __## DataSet__ file, the dataset of this approach is brought. These files are released by the authors, and are available free of charge.

**Data Scaling**

Given the sensitivity of the MLP model to data scaling, I experimented with both Standard Scaler and MinMax Scaler. Results indicate that the Standard Scaler has a more favorable impact on the model's performance.

**Model Evaluation Criteria**

Unlike the original article, my code incorporates detailed criteria for evaluating the machine learning models on both test and train subsets. It is observed that the original article's plots, characterized by small circles and a wider range of axes, might lead to misconceptions about the model's performance. By closely tracking specific data points, my code demonstrates superior performance compared to the original article.
