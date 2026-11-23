# Data dictionary

## `penguins.csv` (notebook 1)

**342 real penguins, 7 columns** from the [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/) dataset (Gorman, Williams & Fraser, Palmer Station LTER). Gaps: `sex` 9, `bill_depth_mm` 3, `flipper_length_mm` 2.

| Column | Type | Meaning |
|---|---|---|
| `species` | category | Adelie, Chinstrap, Gentoo |
| `island` | category | Biscoe, Dream, Torgersen |
| `bill_length_mm` | number | Beak length, mm |
| `bill_depth_mm` | number | Beak depth, mm |
| `flipper_length_mm` | number | Flipper length, mm |
| `sex` | category | Female, Male |
| **`body_mass_g`** | number | **Target.** Weight in grams |

## `beanbox_subscribers.csv` (notebook 3)

**2,000 subscribers, 14 columns.** 24.2% cancelled. Snapshot: **1 Nov 2026**; label: cancelled between 1 and 30 Nov.

> **Synthetic data.** BeanBox is a fictional company. The data was generated for this course so that cancelling depends on being new, being inactive, skipped deliveries, support contacts, ratings, plan and sign-up channel (with jumps, not straight lines). Two columns are **deliberate leaks** for the exercise. Don't draw conclusions about real subscription businesses from it.

| Column | Type | Meaning |
|---|---|---|
| `subscriber_id` | id | Subscriber number |
| `months_subscribed` | number | Months since sign-up, as of 1 Nov |
| `plan` | ordered category | `starter` < `classic` < `barista` |
| `bags_per_month` | number | Bags per delivery |
| `signup_channel` | category | instagram, google_ads, friend_referral, podcast; **empty for 84** (tracking blocked) |
| `country` | category | DE, AT, CH, NL |
| `app_opens_last_4w` | number | App opens in the 4 weeks before 1 Nov |
| `deliveries_skipped_90d` | number | Deliveries skipped in the 90 days before 1 Nov |
| `support_contacts_90d` | number | Support contacts in the 90 days before 1 Nov |
| `avg_bag_rating` | 1–5 | Average stars given to bags; **empty for 1,114** (never rated) |
| `lifetime_spend_eur` | number | Total spent since sign-up (grows with tenure) |
| `days_since_last_order` | number | ⚠️ Computed by the export script on **30 Nov** (after the snapshot): **leak** |
| `exit_survey_done` | 0/1 | ⚠️ Filled in while cancelling: **leak** |
| **`cancelled`** | 0/1 | **Target.** 1 = cancelled between 1 and 30 Nov |

## Snowman data (notebook 2)

14 rows typed directly into the notebook (from the original `ds-feature-engineering` exercise): `temp` (2 gaps), `lunch`, `dinner` (3 gaps), `precipitation`, target `height_snowman_cm`. It's for preparation practice only.
