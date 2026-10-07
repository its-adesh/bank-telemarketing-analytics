# Customer Segmentation

## Purpose

I grouped customers with similar traits to understand how term-deposit subscription rates varied across different customer profiles.

## My approach

I used K-means clustering to create customer groups.

Before clustering, I converted categorical fields into numeric columns and scaled age, balance, and the numeric field `Int.Rate09`.

I excluded the subscription outcome when creating the groups, then used it to compare their subscription rates.

I explored different numbers of clusters using the elbow method and silhouette scores. Five clusters had the highest silhouette score among the options tested, at approximately 0.17.

## Results

Cluster numbers are labels, not rankings. Figures are rounded.

| Customer group | Share of customers | Average age | Subscription rate |
| --- | ---: | ---: | ---: |
| Cluster 0 | 13.9% | 39.0 | 22.7% |
| Cluster 1 | 45.1% | 34.1 | 8.8% |
| Cluster 2 | 29.6% | 52.3 | 9.6% |
| Cluster 3 | 2.4% | 43.5 | 15.1% |
| Cluster 4 | 9.0% | 40.3 | 15.3% |

![Subscription rates by customer group](../reports/figures/cluster_subscription_rates.png)

Cluster 0 had the highest subscription rate. The chart shows proportions, so 0.227 means 22.7%.

## Key findings

- Cluster 0 had the highest subscription rate at 22.7%, while representing 13.9% of customers.
- Cluster 1 accounted for 45.1% of customers but had the lowest subscription rate at 8.8%.
- Cluster 2 had the highest average age, at 52.3 years, and a subscription rate of 9.6%.
- Cluster 3 had the highest average balance, but its subscription rate was lower than Cluster 0's. The group with the highest balance was not the group with the highest subscription rate.

## What this means for campaign planning

The largest customer group did not have the highest subscription rate. This suggests that campaign planning should consider both group size and past subscription behaviour.

I recommend exploring Cluster 0 in a small targeted campaign test. Comparing its subscription rate and cost per subscription with the bank's usual approach would help assess whether targeting this group is worthwhile.

## How I interpret the groups

The silhouette score of 0.17 indicates considerable overlap between the groups. I treat them as broad customer profiles for exploration.

Before using them in regular campaigns, I would check whether similar profiles and subscription patterns appear in newer data.

## Recommended next steps

- Review each group's customer traits in more detail.
- Check whether the groups remain consistent in newer data.
- Test targeted outreach on a small scale.
- Compare subscription rates and contact costs before expanding the campaign.

## Notebook

[View my customer segmentation analysis](../notebooks/01_customer_segmentation.ipynb)
