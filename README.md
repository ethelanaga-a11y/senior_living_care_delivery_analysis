Senior Living Care Delivery & Response Time Analysis

Project Overview

Timely responses to resident care requests are essential for quality of care, resident satisfaction, and operational efficiency in senior living facilities.

This project analyzes a synthetic dataset of 1,000 resident care requests recorded over a 30-day period. The analysis examines care-request volume, response times, and Service Level Agreement (SLA) performance across different times of day and care-request categories.

Statistical hypothesis testing was also performed to determine whether response-time differences between peak and off-peak periods were statistically significant and whether care-request type or day of the week was associated with response performance.

The goal is to identify predictable demand patterns and provide practical recommendations for improving timely care delivery and optimizing existing operational resources.

Business Questions

1. Are resident care requests evenly distributed throughout the day, or do specific periods experience higher demand and longer response times?
2. How can management better align existing caregiver hours with periods of peak resident-care demand to reduce response delays without increasing total staffing or labor costs?

Key Performance Indicators

- Average Response Time: Time between a resident care request and its resolution.
- SLA Breach Rate: Percentage of requests exceeding the 15-minute service-level target.
- Hourly Request Volume: Number of care requests received during each hour of the day.
- Peak vs. Off-Peak Response Time: Comparison of average response times during identified high-demand and lower-demand periods.

Tools & Technologies

- Python
- Pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- Google Colab / Jupyter Notebook

Analysis Performed

Data Preparation

- Converted request and resolution timestamps to datetime format.
- Recalculated response times from timestamps.
- Validated response-time values.
- Created hour-of-day and day-of-week features.
- Created a weekend indicator.
- Created a 15-minute SLA breach indicator.

Statistical Analysis

Welch's Two-Sample t-Test

Compared peak and off-peak response times.

- Peak average response time: 16.50 minutes
- Off-peak average response time: 5.40 minutes
- t-statistic: 25.7931
- p-value: < 0.001

The results provide strong statistical evidence that response times differ between peak and off-peak periods.

Chi-Square Test of Independence

Examined the relationship between care-request type and SLA breach status.

- χ² = 4.64
- p = 0.3264

The result was not statistically significant, indicating insufficient evidence of an association between request type and SLA breach status in this dataset.

One-Way ANOVA

Examined whether response times differed across days of the week.

- F = 0.5312
- p = 0.7848

The result was not statistically significant.

Key Findings

1. Predictable Demand Peaks

Care requests were not evenly distributed throughout the day. The strongest demand occurred during:

- 7:00–9:00 AM
- 6:00–7:00 PM

2. Longer Response Times During Peak Periods

Average response time increased substantially during peak periods:

16.50 minutes peak vs. 5.40 minutes off-peak

The Welch's t-test confirmed that this difference was statistically significant.

3. ADL Assistance and Mobility Transfers Accounted for Many SLA Breaches

ADL Assistance and Mobility Transfer requests together represented 57.80% of all SLA breaches.

However, the Chi-Square test did not find a statistically significant relationship between request type and SLA breach status.

4. Day of Week Was Not a Significant Factor

The ANOVA results showed no statistically significant difference in response times across days of the week.

Overall, time of day appears to be a more important operational consideration than day of week or request category in this dataset.

Recommendations

Based on the findings, senior-living management could consider:

1. Aligning existing caregiver coverage with peak demand periods, particularly 7:00–9:00 AM and 6:00–7:00 PM.
2. Using staggered shifts or targeted shift overlap during predictable demand peaks.
3. Planning for high-volume care activities, particularly ADL Assistance and Mobility Transfers.
4. Scheduling non-urgent administrative activities during lower-demand periods where operationally appropriate.
5. Continuously monitoring response times and SLA breaches to evaluate whether operational changes improve performance.

These recommendations focus on better utilization of existing resources rather than assuming that additional staffing is required.

Visualizations

Care Request Volume vs. Average Response Time

"Care Request Volume vs Response Time" (hourly_demand_vs_response.png)

SLA Breach Rate by Care Request Category

"SLA Breach Rate by Care Request Category" (sla_breach_by_care_type.png)

Dataset

The dataset contains 1,000 synthetic care-request records and includes:

- Request ID
- Resident ID
- Request type
- Request timestamp
- Resolution timestamp
- Response time

The dataset is synthetic and does not represent real residents, employees, or care events. No personally identifiable information is included.

Project Files

- "Senior_Living_Care_Delivery_Response_Time_Analysis.ipynb" — Complete Python analysis and documentation
- "care_requests.csv" — Synthetic dataset
- "hourly_demand_vs_response.png" — Demand and response-time visualization
- "sla_breach_by_care_type.png" — SLA breach visualization

Conclusion

This project demonstrates the use of Python, data cleaning, feature engineering, exploratory data analysis, visualization, and statistical hypothesis testing to investigate an operational problem in a senior-living environment.

The analysis identified predictable periods of higher care demand and demonstrated a statistically significant difference in response times between peak and off-peak periods. These findings can help inform operational decisions around scheduling, workflow coordination, and resource utilization.
