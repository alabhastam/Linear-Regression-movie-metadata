# Movie Revenue Prediction

A machine learning project that predicts movie `revenue` based on five features:
`budget`, `runtime`, `vote_average`, `vote_count`, and `popularity`.

## Dataset
- Source: `movies_metadata.csv`
- Cleaning: converted `budget` and `popularity` to numeric, removed `NaN`
  values, and dropped rows with zero `budget` or `revenue`.
- Final size: 5380 rows.

## Approach
- Split: 70% train / 15% validation / 15% test.
- Model selection: tested polynomial degrees 1–4 on the validation set; `degree=2` had the lowest MSE.
- Trained both Linear Regression and Polynomial Regression (degree 2) with scikit-learn.

## Results
| Model | MSE | R² |
|-------|------|------|
| Linear | 0.2835 | 0.686 |
| Polynomial (deg 2) | 0.2482 | 0.7252 |

The polynomial model performed better. A negative `budget²` coefficient (`-0.0163`)
indicates diminishing returns: revenue rises with budget but the effect flattens out.
