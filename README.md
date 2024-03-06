# Language Model Regressor

This repository presents a simplified version of the paper replication for the research outlined in "OmniPred: Language Models as Universal Regressors" ([link to paper](https://arxiv.org/abs/2402.14547)). In this project, I adapt the concept for a Kaggle competition focused on housing price prediction from tabular data ([Kaggle competition link](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview)).

## Implementation Details

- **Model Selection:** Instead of the T5X model discussed in the paper, this project utilizes the `T5-small` model due to resource constraints.
- **Training Environment:** The model was trained on Google Colab, utilizing a V100 GPU with 16GB of memory. The training was conducted with a batch size of 8.
- **Dataset:** The original paper utilized data from systems optimized using Google Vizier. In contrast, this project applies the concept to the House Prices: Advanced Regression Techniques competition on Kaggle. The competition involves predicting housing prices based on over 70 features. Due to memory and input length limitations, this implementation focuses on 20 features.

## Data Preparation

Each observation in the tabular data is converted into a string representation of a dictionary, where each key corresponds to a column name and each value to the cell value. For example:

```plaintext
{objective:regression, type:housing_price} : {'MSSubClass': 60, 'MSZoning': 'RL', 'LotArea': 8450, 'Street': 'Pave', 'LotShape': 'Reg', 'LandContour': 'Lvl', 'Utilities': 'AllPub', 'LotConfig': 'Inside', 'LandSlope': 'Gtl', 'Neighborhood': 'CollgCr', 'Condition1': 'Norm', 'BldgType': '1Fam', 'HouseStyle': '2Story', 'OverallQual': 7, 'OverallCond': 5, 'YearBuilt': 2003, 'YearRemodAdd': 2003, 'RoofStyle': 'Gable', 'Exterior1st': 'VinylSd', 'Exterior2nd': 'VinylSd', 'ExterQual': 'Gd', 'Foundation': 'PConc', 'TotalBsmtSF': 856, 'GrLivArea': 1710, 'GarageCars': 2}
```

The target value is encoded as a string of numbers in an exponential style, represented with parentheses instead of angles brackets to avoid tokenizer issues with unrecognized tokens:

```plaintext
'(+)(1)(2)(2)(5)(+)(01)'
```

## Results

Using the T5-small model, this approach achieved [INSERT RESULT] on the Kaggle competition, ranking [INSERT RANK]. Despite the constraints, this result is impressive and showcases the potential of language model-based regression models for tabular data prediction tasks.

