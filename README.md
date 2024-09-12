# Vanguard-AB-test

Vanguard believed that a more intuitive and modern User Interface (UI), coupled with timely in-context prompts (cues, messages, hints, or instructions provided to users directly within the context of their current task or action), could make the online process smoother for clients. The critical question is: Would these changes encourage more clients to complete the process?

## A/B Testing
An A/B test was set into motion from 3/15/2017 to 6/20/2017 by the team.
Control Group: Clients interacted with Vanguard’s traditional online process.
Test Group: Clients experienced the new, spruced-up digital interface.
Both groups navigated through an identical process sequence: an initial page, three subsequent steps, and finally, a confirmation page signaling process completion.
The goal is to see if the new design leads to a better user experience and higher process completion rates.

## We have 3 datasets:
1. Client Profiles (df_final_demo): Demographics like age, gender, and account details of our clients.
2. Digital Footprints (df_final_web_data): A detailed trace of client interactions online, divided into two parts: pt_1 and pt_2.
3. Experiment Roster (df_final_experiment_clients): A list revealing which clients were part of the grand experiment.

## To measure the effectiveness of the new User Interface, our KPI are: 
1. Completion Rate: The proportion of users who reach the final ‘confirm’ step.
2. Time Spent on Each Step: The average duration users spend on each step.
3. Error Rates: If there’s a step where users go back to a previous step, it may indicate confusion or an error. You should consider moving from a later step to an earlier one as an error.
4. Time Spent from Start to Confirm Step (additional KPI): The total duration of a process sequence from start to confirm.

## Hypothesis Testing:
### 1. Completion Rate: 
The new design (Test group) has a higher completion rate compared to the old design (Control group). In order to confirm if this difference is statistically significant, we proceeded with a z-test.

### 2. Time Spent on Each Step: t-test

### 3. Error Rates:
The new design (Test group) has a higher Error rate compared to the old design (Control group). In order to confirm if this difference is statistically significant, we proceeded with a z-test with the following hypothesis:

H0 = error rate test group <= error rate control group;
H1 = error rate test group > error rate control group

The null hypothesis is rejected. The error rate in the test group is larger than the control group.

### 4. Time Spent from Start to Confirm Step (additional KPI):
Total time spent from start page to confirm page for one visit_id per client_id. 
For each visit_id, we take the earliest 'start' and the last 'confirm'. If a visit has no start or confirm we can ignore them.
Visits going to a confirm step before a start step will be ignored and considered as errors.

When calculating the total duration, we removed negative values considered as errors and removed outliers using the IQR technique.
The average total duration for the Control group is slightly higher than the Test group. In order to confirm if this difference is statistically significant, we proceeded with a t-test with the follwing hypothesis:

H0 = average_total_duration_test_group <= average_total_duration_control_group;
H1 = average_total_duration_test_group > average_total_duration_control_group

The null hypothesis is rejected. The control group spends less total time on average than the test group.

## Experiment Evaluation

### Design Effectiveness
Clients were equally divided between the old and new designs. Characteristics like gender, tenure, accounts balance, online logs and calls were proportionally represented in both experiment groups.

### Duration Assessment
The experiment was done over a short time period, hence, the error rates and completion is high, not specifically because of the new UI being less effective, but because it always takes time to get comfortable with a new interface.

## Additional content

### Tableau link
