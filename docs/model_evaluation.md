# Subscription Prediction: Model Evaluation

## Purpose

Explore whether prediction models could help a bank identify customers who are likely to subscribe to a term deposit.

## How the models were tested

The data was split into 80% for training and 20% for testing, keeping a similar share of subscribers in both sets.

The test set contained 9,043 records, including 1,058 subscribers. Call duration was excluded from the model inputs.

## Why accuracy was not enough

Only about 11.7% of customers subscribed. Predicting “no” for every customer would achieve around 88.3% accuracy while missing every subscriber.

I therefore reviewed precision, recall, and F1-score alongside accuracy.

- **Precision:** Of the customers predicted to subscribe, how many actually subscribed?
- **Recall:** Of all actual subscribers, how many did the model identify?
- **F1-score:** A measure that balances precision and recall.

## Results

Precision, recall, and F1-score below refer to the subscriber class. Figures are rounded from the saved notebook outputs.

| Model | Accuracy | Precision | Recall | F1-score |
| --- | ---: | ---: | ---: | ---: |
| Logistic Regression | 89.4% | 68% | 18% | 0.28 |
| Random Forest | 88.3% | 50% | 21% | 0.29 |
| Decision Tree | 82.4% | 28% | 32% | 0.30 |
| XGBoost | 89.0% | 57% | 23% | 0.33 |
| LightGBM | 89.4% | 64% | 21% | 0.31 |
| LightGBM with class weighting | 80.4% | 32% | 61% | 0.42 |

This table shows the initial models and the weighted LightGBM model explored further in the analysis. Additional weighted models are available in the notebook.

## What class weighting changed

Giving more weight to subscribers during training helped LightGBM identify more of them.

On the same test set:

- Standard LightGBM identified 220 of 1,058 subscribers and incorrectly flagged 124 non-subscribers.
- Weighted LightGBM identified 641 subscribers and incorrectly flagged 1,355 non-subscribers.

Recall increased from around 21% to 61%, but precision fell from 64% to 32%.

The weighted model also achieved a ROC-AUC score of 0.7752, which measures how well it ranks subscribers above non-subscribers across different thresholds.

## Business meaning

The weighted model found more potential subscribers, but also produced a longer list of customers who did not subscribe.

Choosing a model depends on the campaign goal and budget. A team with limited calling capacity may value precision more, while a team aiming to reach more potential subscribers may accept lower precision for higher recall.

These test results do not show actual campaign savings or extra subscriptions.

## Next steps

- Compare prediction thresholds against available calling capacity.
- Estimate contact costs and the value of a subscription.
- Validate performance on a later period of data.
- Run a small campaign test before wider use.

## Notebook

[View the subscription prediction analysis](../notebooks/02_subscription_prediction.ipynb)
