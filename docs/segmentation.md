# Customer Segmentation

## Purpose

Understand which customers share similar traits and compare their term-deposit subscription rates.

## Approach

I used K-means clustering to group customers. Categorical fields were converted into numeric columns, and age, balance, and interest rate were scaled.

The subscription outcome was excluded when creating the groups. It was then used to compare subscription rates across them.

I explored different numbers of clusters using the elbow method and silhouette scores. Five clusters had the highest silhouette score among the options tested, at approximately 0.17.

## Results

Group numbers are labels, not rankings.

| Customer group | Share of customers | Average age | Subscription rate |
| --- | ---: | ---: | ---: |
| Cluster 0 | 13.9% | 39.0 | 22.7% |
| Cluster 1 | 45.1% | 34.1 | 8.8% |
| Cluster 2 | 29.6% | 52.3 | 9.6% |
| Cluster 3 | 2.4% | 43.5 | 15.1% |
| Cluster 4 | 9.0% | 40.3 | 15.3% |

Figures are rounded and come from the saved clustering notebook.

## Main findings

- Cluster 0 had the highest subscription rate, although it represented only 13.9% of customers.
- Cluster 1 was the largest group but had the lowest subscription rate.
- Cluster 3 had the highest average balance, but its subscription rate was below Cluster 0. A higher balance alone did not identify the group with the highest subscription rate.

## Business use

Cluster 0 could be a starting point for a small targeted campaign test. The bank could compare its response rate and cost per subscription with its usual approach.

The largest group should not automatically receive the most attention. Group size and likelihood of subscribing both matter when planning outreach.

## Limitations

The silhouette score of 0.17 suggests considerable overlap between the groups. These segments are useful for exploration, but need further validation before being used in campaigns.

The subscription rates describe historical patterns. They do not prove that targeting a group will increase subscriptions.

## Notebook

[View the customer segmentation analysis](../notebooks/01_customer_segmentation.ipynb)
