## Diamond Price Prediction -Ashish Birla
### Introduction About the Data :
<b>The Dataset</b>
 The goal is to predict price of given diamond (Regression Analysis).

There are 10 independent variables (including id):

<b>id</b> : unique identifier of each diamond <br> 
<b>carat</b> : Carat (ct.) refers to the unique unit of weight measurement used exclusively to weigh gemstones and diamonds.<br> 
<b>cut</b>: Quality of Diamond Cut <br> 
<b>color</b> : Color of Diamond <br> 
<b>clarity</b> : Diamond clarity is a measure of the purity and rarity of the stone, graded by the visibility of these characteristics under 10-power magnification.<br> 
<b>depth</b> : The depth of diamond is its height (in millimeters) measured from the culet (bottom tip) to the table (flat, top surface) <br> 
<b>table</b> : A diamond's table is the facet which can be seen when the stone is viewed face up.<br> 
<b>x</b> : Diamond X dimension <br> 
<b>y</b> : Diamond Y dimension <br> 
<b>z</b>: Diamond Z dimension <br> 
<br>
Target variable:

<b>price</b>: Price of the given Diamond.



# Screenshot of UI <br>



![Screenshot (1437)](https://github.com/AaBirla/DiamondPricePredictionproject/assets/119050112/6d1c555b-b305-4364-aa0b-e3f37db6726a)



# Approach for the project
## Data Ingestion :

In Data Ingestion phase the data is first read as csv.<br>
Then the data is split into training and testing and saved as csv file.<br>
## Data Transformation :

In this phase a ColumnTransformer Pipeline is created.<br>
for Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.<br>
for Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.<br>
This preprocessor is saved as pickle file.<br>
## Model Training :

In this phase base model is tested . The best model found was Lasso.<br>
After this hyperparameter tuning is performed on 'LinearRegression', 'Lasso', 'Ridge', 'Elasticnet'.<br>
A final VotingRegressor is created which will combine prediction of 'LinearRegression', 'Lasso', 'Ridge', 'Elasticnet'.<br>
This model is saved as pickle file.<br>
## Prediction Pipeline :

This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.<br>
## Flask App creation :

Flask app is created with User Interface to predict the diamond prices inside a Web Application.<br>


# Exploratory Data Analysis Notebook <br>
link:https://vscode.dev/github/AaBirla/DiamondPricePredictionproject/blob/main/notebooks/EDA.ipynb

# Model Training Approach Notebook <br>
link:https://vscode.dev/github/AaBirla/DiamondPricePredictionproject/blob/main/notebooks/Model%20Training.ipynb
