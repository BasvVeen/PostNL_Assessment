### Overview repository
This is the repository for the coding Assessment for my PostNL application for the role of Junior Data Scientist.

The Assessment.ipynb contains the analysis, feature engineering, and model code, written in the format of a jupyter notebook. To run the code, open the notebook in an interpreter and run pip install requirements.txt in the terminal to recreate the virtual environment I worked in. The dataset is called parcel_delivery_dataset.csv. If you download the repository as a zip file, you can run everything from within that folder. 

### Explanation of approach and insights gained
For this assessment I have performed EDA by checking for missing values, misspellings of categories, duplicate rows, and looked at the distribution of the features, both the numeric and categorical ones. I have found that the deliverytime__window is balanced for prediction, and that the supplied data is clean. 

I have done feature selection and engineering by looking at the different chi2 scores of the features, and selecting the 5 features with the highest score. The 'hour' feature had the largest score by far, and I found when looking at the feature importance of the features of the RandomForest and XGBoost that the feature is by far the most important for the prediction. This means that the other features lose a lot of their impact, which could worsen performance and predictive power. This is the case with all three models.

I have compared three models: A Neural Network, a RandomForest classifier, and XGBoost. The NN consists of one input layer, one hidden layer, one output layer and two dropout layers to prevent overfitting. Additionaly, I have added regularization to try to reduce the importance of the hour feature. The evaluation of all models is done with kFold cross-validation to avoid overfitting. 

I have found that the accuracy of all three models is similar, with very minimal differences. The RandomForest and XGBoost classifiers have a reasonable AUC though (~0.74), so they are able to distinguish between the categories reasonably well. 
