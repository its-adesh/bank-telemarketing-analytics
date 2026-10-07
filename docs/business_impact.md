# Business Impact and Recommendations

## What the analysis suggests

My analysis found differences in subscription rates across customer groups. The weighted model identified more subscribers but also incorrectly flagged more non-subscribers. Based on these results, I recommend testing targeted outreach before expanding the campaign.

## Recommendations

### 1. Test outreach to the highest-response group

Cluster 0 had a historical subscription rate of 22.7%, the highest of the five groups.

Explore this group in a small campaign test before committing a larger budget. Its past performance does not guarantee the same result in a future campaign.

### 2. Match targeting to calling capacity

Weighted LightGBM identified more actual subscribers, but also flagged more non-subscribers.

Choose the prediction threshold based on how many customers the team can contact, the cost of each contact, and the expected value of a subscription.

### 3. Validate the customer groups

The clusters overlapped considerably. Check whether their profiles and subscription patterns remain similar in newer data before using them for regular campaign planning.

## Suggested campaign test

- Define which customers are eligible for the campaign.
- Compare model-based targeting with the bank's usual targeting approach.
- Randomly assign comparable customer pools to the two approaches.
- Keep contact budgets, offers, and campaign timing similar.
- Set the success measures before starting.
- Compare results before expanding the approach.

## How to measure success

| Measure | What it tells the bank |
| --- | --- |
| Subscription rate | The share of contacted customers who subscribe |
| Cost per subscription | Total campaign cost divided by subscriptions gained |
| Subscriptions per 100 calls | How effectively the team uses calling capacity |
| Incremental subscriptions | Extra subscriptions compared with the usual approach, allowing for differences in group size |
| Net campaign value | Estimated value from subscriptions minus campaign costs |

## Information needed

A financial estimate would require:

- Average contact cost.
- Available calling capacity.
- Expected net value of a term-deposit subscription.
- Results from the bank's usual campaigns.
- Results from the proposed campaign test.

## Limits

This project uses historical data and saved model results. No live campaign was run, and no actual increase in subscriptions, cost savings, or return on investment was measured.

## Supporting analysis

- [Customer segmentation](segmentation.md)
- [Model evaluation](model_evaluation.md)

