# Data Dictionary

This guide explains the dataset columns and how they were prepared for analysis.

## Customer details

| Column | Meaning |
| --- | --- |
| age | Customer age in years |
| job | Job category |
| marital | Marital status |
| education | Education category |
| default | Whether the customer has credit in default |
| balance | Average yearly balance, in euros, according to the standard dataset definition |
| housing | Whether the customer has a housing loan |
| loan | Whether the customer has a personal loan |

## Contact history

| Column | Meaning |
| --- | --- |
| contact | Communication channel |
| day | Day of the month of the last contact |
| month | Month of the last contact |
| duration | Length of the last contact, in seconds |
| campaign | Number of contacts in the current campaign for this customer |
| pdays | Days since contact in a previous campaign; -1 means no previous contact |
| previous | Number of contacts before the current campaign |
| poutcome | Outcome of the previous campaign |

## Subscription outcome

| Column | Meaning |
| --- | --- |
| y | Whether the customer subscribed to a term deposit |

The notebooks convert `yes` to 1 and `no` to 0.

For prediction, `y` is the target. For clustering, it is excluded from the inputs and used afterwards to compare subscription rates.

## Additional fields

The project workbook contains two fields that are not part of the standard bank-full field list.

| Column | Use in the notebook |
| --- | --- |
| Int.R08 | Removed during preparation |
| Int.Rate09 | Retained as a numeric input |

Their exact definitions, units, and source need to be confirmed from the original workbook documentation.

## Fields created during preparation

### pdays_category

Groups customers by time since previous contact:

| Original value | Category |
| --- | --- |
| -1 | Never Contacted |
| 1–30 days | Recent Engagement |
| 31–180 days | Moderate Engagement |
| 181–365 days | Low Engagement |
| More than 365 days | Dormant Customers |
| Other values | Other |

These are labels used in the notebook. They describe contact timing, not measured customer engagement.

### previous_category

Groups customers by the number of previous contacts:

| Original value | Category |
| --- | --- |
| 0 | No Previous Contact |
| 1–5 | Low Previous Contact |
| 6–10 | Moderate Previous Contact |
| 11–20 | High Previous Contact |
| 21 or more | Very High Previous Contact |
| Other values | Other |

## Preparation notes

- Removed `Int.R08`, `day`, `month`, `duration`, and `campaign`.
- Replaced `pdays` and `previous` with the categories above.
- Converted categorical inputs into numeric indicator columns using one-hot encoding.
- Applied scaling before modelling.

Excluding call duration avoids using information that would only be available after a call.

## Reference

Standard field descriptions were checked against the [UCI Bank Marketing documentation](https://archive.ics.uci.edu/dataset/222/bank). The extra fields in the project workbook require separate confirmation.
