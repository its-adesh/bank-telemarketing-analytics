# Data Dictionary

This guide explains the fields I used and how I prepared them for analysis.

## Customer details

| Column | Meaning |
| --- | --- |
| age | Customer age in years |
| job | Job category |
| marital | Marital status |
| education | Education category |
| default | Whether the customer has credit in default |
| balance | Average yearly balance in euros |
| housing | Whether the customer has a housing loan |
| loan | Whether the customer has a personal loan |

## Contact history

| Column | Meaning |
| --- | --- |
| contact | Communication channel |
| day | Day of the month of the last contact |
| month | Month of the last contact |
| duration | Length of the last contact in seconds |
| campaign | Number of contacts in the current campaign for this customer, including the last contact |
| pdays | Days since contact in a previous campaign; -1 means no previous contact |
| previous | Number of contacts before the current campaign |
| poutcome | Outcome of the previous campaign |

## Subscription outcome

| Column | Meaning |
| --- | --- |
| y | Whether the customer subscribed to a term deposit |

I converted `yes` to 1 and `no` to 0.

I Used `y` as the target for prediction. For clustering, I excluded it from the inputs and used it afterwards to compare subscription rates across the groups.

## Additional workbook fields

| Column | How I used it |
| --- | --- |
| Int.R08 | Removed during preparation |
| Int.Rate09 | Retained as a numeric input |

## Fields I created

### pdays_category

I grouped customers by the time since their previous contact.

| Original value | Category |
| --- | --- |
| -1 | Never Contacted |
| 1–30 days | Recent Engagement |
| 31–180 days | Moderate Engagement |
| 181–365 days | Low Engagement |
| More than 365 days | Dormant Customers |
| Other values | Other |

Used these labels to describe contact timing. They do not measure customer interest or engagement directly.

### previous_category

I grouped customers by their number of previous contacts.

| Original value | Category |
| --- | --- |
| 0 | No Previous Contact |
| 1–5 | Low Previous Contact |
| 6–10 | Moderate Previous Contact |
| 11–20 | High Previous Contact |
| 21 or more | Very High Previous Contact |
| Other values | Other |

## Data preparation

- Removed `Int.R08`, `day`, `month`, `duration`, and `campaign`.
- Replaced `pdays` and `previous` with the categories above.
- Converted categorical inputs into numeric indicator columns using one-hot encoding.
- Applied scaling before modelling.

Call duration is only available after a call, so excluding it keeps that information out of predictions intended for use before contact.

## Reference

[UCI Bank Marketing dataset documentation](https://archive.ics.uci.edu/dataset/222/bank)
