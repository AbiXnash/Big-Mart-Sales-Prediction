# Big-Mart-Sales-Prediction

Predicts `Item_Outlet_Sales` for the [Big Mart Sales](https://www.kaggle.com/datasets/brijbhushannanda1979/bigmart-sales-data)
dataset with a Random Forest, in one Google Colab notebook.

## What the notebook does

1. Loads `train_ds.csv.zip` and `test_ds.csv.zip` and fills missing `Item_Weight` and `Outlet_Size` values.
2. Groups `Item_Type` into foods, drinks and non-consumables (from the `Item_Identifier` prefix) and cleans
   `Item_Fat_Content` (non-consumables get their own class).
3. Replaces zero `Item_Visibility` with the mean and adds `Years_of_Operation` (up to 2013, the dataset's year).
4. One-hot encodes the categorical columns and scales the features.
5. Trains `RandomForestRegressor` on a 90/10 split, prints MAE, MSE, RMSE and R², and tunes it with `GridSearchCV`.

## Run it

The notebook was written for Colab: it reads the data from `/content/` and mounts Google Drive. To run it locally,
download the dataset and change the two `read_csv` paths.

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook Big_Mart_Sales_Prediction.ipynb
```

The dataset isn't included in this repository.

## Licence

MIT, see [LICENSE](LICENSE).
