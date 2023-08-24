# A/B test analysis — New recommendational funnel

## Used tools: 
* `pandas`
* `matplotlib`
* `seaborn`
* `numpy`
* `scipy`
* `datetime`
* `math`
* `plotly`

## Project description

Evaluate whether the changes associated with the implementation of an improved recommendation system for users have been beneficial.

The client has access to a datasets with anonymized user data of maden A/B test.

**Datasets and Columns:**
**`ab_project_marketing_events.csv`** — a calendar of marketing events for the year 2020.
- `name` — the name of the marketing event;
- `regions` — the regions where the advertising campaign will be conducted;
- `start_dt` — the start date of the campaign;
- `finish_dt` — the end date of the campaign.

**`final_ab_new_users.csv`** — users who registered from December 7th to December 21st, 2020.
- `user_id` — user identifier;
- `first_date` — registration date;
- `region` — user's region;
- `device` — device from which the registration was performed.

**`final_ab_events.csv`** — actions of new users from December 7th, 2020 to January 4th, 2021.
- `user_id` — user identifier;
- `event_dt` — event date and time;
- `event_name` — type of event;
- `details` — additional data about the event. For example, for purchases, the cost of the purchase in dollars is stored in this field.

**`final_ab_participants.csv`** — table of test participants.
- `user_id` — user identifier;
- `ab_test` — test name;
- `group` — user group.

## Technical Specification

- Test name: `recommender_system_test`
- Groups: A (Control), B (New Payment Funnel)
- Launch date: 2020-12-07
- Stop date for new user acquisition: 2020-12-21
- Stop date: 2021-01-04
- Audience: The test should include 15% of new users from the EU region.
- Test purpose: Testing changes associated with the implementation of an improved recommendation system.
- Expected number of participants: 6000
- Expected effect: Within 14 days from the registration date, users should demonstrate an improvement in each metric by at least 10%:
    - Conversion to product page views - event `product_page`
    - Cart views - `product_cart`
    - Purchases - `purchase`


## Overall conclusion

Four datasets were obtained, studied, and processed:

* **data_events**
1. The nature of missing values is clear: additional information in case of a purchase;
2. Discrepancy in the dates according to the task: The task specifies from December 7, 2020 to January 4, 2021, while the actual data is from December 7, 2020 to December 30, 2020 (We conclude that the dataset is incomplete or there are errors in the task).
3. The date December 30 is incomplete in the dataset, with only 89 actions recorded. It is possible that this day should be excluded from the analysis.
4. The distribution of events by date shows two spikes in activity: December 14 and December 21.

* **data_users**
1. Users are distributed among 4 regions, with the European region being the most prevalent.
2. Discrepancy in the dates according to the task: The task specifies from December 7, 2020 to December 21, 2020, while the actual data is from December 7, 2020 to December 23, 2020 (We conclude that the dataset is extended).
3. Registration spikes occur on December 14 and December 21. These dates may have been holidays. Additionally, there is another spike on December 7.

* **data_participants**
1. Another discrepancy with the technical task: the data contains two tests - **'recommender_system_test' (the one we need)** and 'interface_eu_test'.
2. A new dataset was created containing only users participating in the 'recommender_system_test' (Groups A and B).

* **data_mark_events**
1. Two events were identified that could affect the A/B test: Christmas&New Year Promo for the EU and N.America regions from December 25, 2020, to January 2, 2021; CIS New Year Gift Lottery from December 30, 2020, to January 7, 2021.

Based on the results of the exploratory data analysis, the following conclusions were drawn:

1. **The A/B test is conducted with errors:**
* Two marketing events took place during the test period (Christmas&New Year Promo for the EU and N.America regions from December 25, 2020, to January 2, 2021; CIS New Year Gift Lottery from December 30, 2020, to January 7, 2021).
* The data is incomplete (no data for December 30, 2020, to January 4, 2021).
* The number of participants in the test groups differs by almost three times (A: 2082, B: 706).

2. **Results of the analysis of event funnels for groups A/B:**
* After logging in, 65/56% of users proceed to the next step (35/44% drop at this step);
* 46/49% of users view the cart (30/28% of the initial number of users);

**Interesting observation:** Users view the cart less frequently than they make a purchase. This could be due to the presence of a quick purchase button on the website.
* Users purchase products at a rate of 103/102% compared to those who view the cart (31/28% of the initial number of users).
___
**In summary:** The implementation of the new payment funnel is not effective.
