# Data Cleaning, Preprocessing & EDA (Bengaluru Housing + Titanic)

Hands-on notebooks covering the full data-preparation workflow in Python: loading raw data, finding and fixing missing values, cleaning messy text columns, encoding categories, scaling features, detecting outliers, running a basic hypothesis test and splitting data for modelling.

## Datasets
| File | Rows × Columns | Description |
|---|---|---|
| `Bengaluru_House_Data.csv` | 13,320 × 9 | House listings in Bengaluru: area type, availability, location, size (BHK), society, total sqft, bathrooms, balconies, price (₹ lakh) |
| `Titanic_Dataset.csv` | 891 × 12 | Passenger details and survival outcome |

## Notebooks
**`check_null_value.ipynb`**: Pandas fundamentals on the Titanic data. Selecting columns, `loc`/`iloc`, filtering with conditions, sorting, `groupby` summaries (e.g. average fare by class and gender), `value_counts`, renaming columns, type casting and handling nulls.

**`data_preprocessing.ipynb`**: End-to-end cleaning of the Bengaluru dataset.
- **Missing values:** `bath` (73) and `balcony` (609) filled with the mean. `location` (1) and `size` (16) filled with the mode. `society` dropped because 5,502 of 13,320 values (41%) were missing.
- **Messy area column:** `total_sqft` had ranges like `2100 - 2850`. A custom function converts ranges to their midpoint and text to numbers.
- **Encoding:** Label Encoding for `area_type`; One-Hot Encoding (`pd.get_dummies`) for `location` and `availability`.
- **Scaling:** comparison of Min-Max scaling vs Standard scaling.
- **Outliers:** IQR method (Q1 − 1.5×IQR, Q3 + 1.5×IQR).
- **Statistics:** one-sample t-test with `scipy.stats`.
- **Train–test split:** 80/20 using `train_test_split` (10,656 train / 2,664 test rows).

## Tech stack
Python · Pandas · NumPy · scikit-learn (LabelEncoder, MinMaxScaler, StandardScaler, train_test_split) · SciPy · Matplotlib

## How to run
```bash
pip install pandas numpy scikit-learn scipy matplotlib
jupyter notebook
```
