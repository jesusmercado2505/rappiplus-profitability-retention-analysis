# RappiPlus: Profitability, Conversion, and User Retention Analysis | TripleTen Data Analytics Bootcamp (2026)

Comprehensive analysis of RappiPlus performance during the first half of 2025, using sales, product catalog, marketing spend, and user behavior data. The project combines data cleaning, business analysis, SQL queries, statistical experimentation, and Power BI visualization to identify opportunities to improve profitability and the purchasing experience.

---

## Technologies & Skills

| Area | Details |
|---|---|
| **Python** | Pandas and NumPy for data cleaning, transformation, and integration; Matplotlib and Seaborn for exploration and visualization |
| **SQL & PostgreSQL** | Queries on event, user, and activity data to analyze conversion and retention |
| **SQLAlchemy** | Connecting Python to the database |
| **Statsmodels** | Two-proportion Z-test to evaluate an A/B experiment |
| **Power BI** | Relational data modeling, shared date and country dimensions, year-to-date metrics, filters, and drill-through navigation |
| **Analytical skills** | Data quality validation, KPI calculation, margin analysis, conversion funnels, cohort analysis, and actionable business recommendations |

---

## Key Questions

- What data quality issues exist, and how could they affect the results?
- How much profit does the business generate after product costs and marketing spend?
- Which products generate the most sales, and which have margin problems?
- At which stage of the purchasing process does the largest user drop-off occur?
- How does user activity evolve during the first few weeks after registration?
- Does the new checkout interface produce a statistically significant change in conversion?

---

## Methodology

1. **Data quality assessment and cleaning.** Reviewed duplicates, dates, categorical values, missing data, and monetary consistency. Excluded records with invalid quantities and recovered missing marketing channels from campaign identifiers.
2. **Profitability and sales analysis.** Combined orders with product catalog costs to calculate revenue, product costs, profit after marketing, average order value, units sold, and marketing spend by channel.
3. **Conversion funnel analysis.** Queried unique users across six events, from first visit to purchase, to identify drop-offs between stages and potential tracking issues. The analysis uses event-level user counts rather than a validated sequential funnel for each user.
4. **Cohort retention analysis.** Grouped users by registration month and calculated the percentage active in weeks 1, 2, and 3.
5. **A/B experiment evaluation.** Compared conversion rates between the control and treatment interfaces using a two-sided, two-proportion Z-test at a 5% significance level.
6. **Results communication.** Developed a three-page Power BI dashboard featuring an executive overview, product-level analysis, and order-level drill-through.

---

## Conclusions and Recommendations

### Key Findings

- **Positive profit after marketing:** revenue reached $9.49 million, compared with $3.78 million in product costs and $2.87 million in marketing spend. Calculated profit was $2.84 million, excluding other operating expenses not included in the data.
- **Loss-making product:** `Laptop-Gaming-16GB` recorded a gross loss of approximately $91,602, despite generating around $1.08 million in revenue.
- **Main checkout friction:** the largest decline between stage counts occurred between starting checkout and entering payment information: 958 users, equivalent to 13.3% of those who started checkout.
- **Stable weekly retention:** approximately 42% of users in each cohort were active during the weeks analyzed, with no marked decline between weeks 1 and 3. This measures weekly activity, not necessarily continuous engagement by the same users.
- **Inconclusive A/B experiment:** conversion was 15.69% in the control group and 16.29% in the treatment group. The 0.60-percentage-point difference was not statistically significant (p = 0.416).
- **Measurement limitation:** some users added products to their carts without a preceding item-selection event, so funnel rates should be interpreted cautiously.

### Strategic Recommendations

- **Address negative product margins:** review pricing, discounts, and costs for `Laptop-Gaming-16GB`, and assess margin improvement opportunities for high-volume products such as `Blender-XL-Red` and `Jacket-Winter-M`.
- **Prioritize checkout improvements:** investigate why users abandon the process before entering payment information and test targeted solutions to reduce friction.
- **Avoid deploying the new interface solely on the observed uplift:** define a minimum meaningful effect and the required sample size before conducting another experiment.
- **Improve funnel instrumentation:** validate event tracking and reconstruct sequential journeys by user or session, rather than relying on artificially capped conversion rates.
- **Extend retention monitoring:** analyze longer periods and segment users by country, device, and acquisition channel to guide reactivation initiatives.
- **Keep profit metrics clearly separated:** distinguish gross profit from profit after marketing in the dashboard, and avoid allocating marketing spend to products without a validated attribution method.
