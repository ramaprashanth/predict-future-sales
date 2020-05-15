# Predict Future Sales

This project is for the [Kaggle Competition](https://www.kaggle.com/c/competitive-data-science-predict-future-sales)

The goal is to predict total sales for every product and store in the next month. By solving this competition you will be able to apply and enhance your data science skills.

This project consists of three stages:
1. EDA
2. Feature Engineering
3. Modeling

Each stage is implemented in a separated jyputer notebook. 
These can be imported and run directly on *colab.google.com* to implement all stages.
For a good experience, test this project using *colab.google.com*.

You need to get a `username` and `API token` form kaggle and inject them in the notebooks to be able to download the contest data.

I used google drive to store and read output data from different stages.

If you want to use colab.google.com to run this project, make sure you have this folder structure in your google driver(Colab Notebooks):

.
+-- models

+-- submissioms

+-- data

|    +-- prep

+-- modeling.ipynb

+-- feature_engineering.ipynb

+-- eda.ipynb

If you want to use you machine to run this project, make sure you have the previous folder structure, but you need to change to value of the global variables(model_path, data_path, sub_path) in each notbook to suit the new location in your local machine.


**EDA**:

We explore the data, clean it and perform some prepocessing to textual data.
input: contest data
output: cleaned, preprocessed contest data

**Feature Engineering**:

We generate all possible features from the data
input: cleaned, preprocessed contest data
output: train, validation and test set combianed in one grid

**Modeling**:

We build 6 base models(lightGBM, Catboost, LinearRegression, LassoRegression, NerualNetwork, XGBoost)
Then we stack them using Linear Regression meta model.
To test stage, you need to generate the training set (grid_full.pkl) from the previous stage.
You don't need to train the base models (I uploaded them for you)
Generating meta features will take so much time (~12) hours. I don't recommend you to go through it. 
input: training gird
output: trained base models, meta feature(training, validation, test)


## References
1. https://www.kaggle.com/c/competitive-data-science-predict-future-sales
2. https://www.aaai.org/ocs/index.php/FLAIRS/FLAIRS17/paper/download/15508/14934
3. https://ieeexplore.ieee.org/document/8659115
4. http://cs229.stanford.edu/proj2015/193_report.pdf
5. http://xgboost.readthedocs.io/en/latest/parameter.html 