# Bank Telemarketing Analytics

A business analytics project exploring customer behaviour and term-deposit subscriptions to help inform bank marketing decisions.

## Business problem

Contacting every customer takes time and resources. This project explores how customer data could help a bank decide who to contact and how to tailor its campaigns.

## Key questions

- Which customer groups have higher subscription rates?
- What customer traits are linked to subscriptions?
- Can prediction models help identify potential subscribers?
- How could these findings support campaign planning?

## My approach

### Understanding customer groups
Used K-means clustering to group customers with similar traits, then compared their profiles and subscription rates.

### Predicting subscriptions
Compared several models to estimate which customers were likely to subscribe to a term deposit.

Reviewed precision and recall alongside other measures to understand the trade-off between contacting unlikely subscribers and missing potential customers.

### Explaining the results
Used charts and SHAP analysis to explore what influenced model predictions and make the results easier to explain.

## Business relevance

The analysis could help a marketing team:

- Prioritise customer groups for outreach.
- Tailor messages to different customer profiles.
- Make more informed decisions about campaign resources.
- Plan targeted campaigns for further testing.

These are potential uses of the analysis. The project does not measure actual campaign savings or increases in subscriptions.

## Tools used

- Python for data preparation, customer segmentation, and prediction.
- Matplotlib and Seaborn for charts.
- SHAP for explaining model predictions.
- Tableau for exploring customer data.

## Explore the analysis

- [Customer segmentation notebook](notebooks/01_customer_segmentation.ipynb)
- [Subscription prediction notebook](notebooks/02_subscription_prediction.ipynb)

## Project status

The notebooks are available now. Reports, key findings, charts, and supporting documentation will be added next. The Tableau workbook will be added once repaired.

## Acknowledgement

AI tools helped with code development, debugging, and documentation. I reviewed, tested, and ran the code.
