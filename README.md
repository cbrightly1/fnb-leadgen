# fnb-leadgen 
This project uses a logistic regression model to develop a cross-sell list with current mortgage customers. Developed in Jupyter Notebook using Python for FNB.

Our data science team currently has a suite of cross sell models for the various products offered at the bank. It came to our team's attention that over half of our mortgage customers were mortgage only customers. We were not sure how this was effecting the cross-sell model so my partner and I were tasked with the project. This involved building a logistic regression model for two datasets: one where the mortgage only customers were included and another with them excluded. The two models were then compared using precision, recall, and F1 scores. Finally, the customers were deciled and the lift was calculated to make a customer 'lead' list.

## Project Process Overview
1. The data was gathered using SQL Service Management Studio.
2. We used pandas to combine the multiple data tables together, clean up missing values, establish the binary response variable, and consolidate categorical demographic variables.
3. Visualizations were used to explore the data set. Many categorical variables were unbalanced between categories.
4. It was discovered that the small proportion of mortgage customers made the data unbalanced. Oversampling and undersampling techniques were implemented to see which balancing method produced a better result. However, the size of the dataset and the lack of computing power made the oversampling method extremely slow. So the final model utilizes the undersampling method.
5. The data was standardized and split into train, test, and validation sets.
6. For both datasets, the traiing set was split using stratified K-fold cross validation. Then a logistic regression model was fit to each fold. The model with the highest precision was selected to be the final model.
7. Precision, recall, F1 scores, AUC score, and the confusion matrix were calculated for both models. 
8. The data was deciled and the lift was calculated to make a 'lead' list
9. The error metrics and lift distribution determined the final result.

## Project Highlights
- Considerable effort was used to determine which logistic regression algorithm should be used. The Logit packages had p-values built in, but the sklearn model had the metrics. In the end variable importance was not considered since the current model included every variable, so the sklearn model was utilized.
-  Our manager was very happy with our optimized code. Consequently, he asked us to translate the code to Spyder so he can use it as the framework for the production models in the entire model suite.
