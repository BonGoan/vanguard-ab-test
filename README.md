# Vanguard-AB-test by Lucie Stenger and Nicole Pinto

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
The new design (Test group) has a higher completion rate compared to the old design (Control group). In order to confirm if this difference is statistically significant, we proceeded with a z-proportions test, one tailed test.
#H0 = completion rate test group <= completion rate control group #H1 = completion rate test group > completion rate control group
The null hypothesis is rejected. The completion rate in the test group is significantly higher than in the control group.
Completion rate (Test group): 58.52%
Completion rate (Control group): 49.85%

Part 2: Assessing the practical significance with 5% Threshold
#H0 = The increase in the Test group’s completion rate is less than 5% #H1 = The increase in the Test group’s completion rate is greater than or equal to 5%.
Test-conducted: One-tailed z-proportions test
Results: The completion rate in the test group is significantly higher than in the control group.
The observed increase of 8.67% meets or exceeds the 5% threshold. The new design is cost-effective.

### 2. Error Rates:
The new design (Test group) has a higher Error rate compared to the old design (Control group). In order to confirm if this difference is statistically significant, we proceeded with a z-test with the following hypothesis:

H0 = error rate test group <= error rate control group;
H1 = error rate test group > error rate control group

The null hypothesis is rejected. The error rate in the test group is larger than the control group.

### 3. Average Time Spent on Each Step: two sample t-test
We removed the ouliers inorder to since we wanted to compare the mean values across the experiment groups. The goal was to assess the efficiency of the process and to determine if the changes reduce the time spent per step. 
#H0: average_durations_test_group <= average_durations_control_group
#H1: average_durations_test_group > average_durations_control_group 

Failled to reject the null hypothesis. p=0.25 suggesting that when H0 = True, you have a 25%  chance to find a sample like the one you have found.

### 4. Time Spent from Start to Confirm Step (additional KPI):
Total time spent from start page to confirm page for one visit_id per client_id. 
For each visit_id, we take the earliest 'start' and the last 'confirm'. If a visit has no start or confirm we can ignore them.
Visits going to a confirm step before a start step will be ignored and considered as errors.

When calculating the total duration, we removed negative values considered as errors and removed outliers using the IQR technique.
The average total duration for the Control group is slightly higher than the Test group. In order to confirm if this difference is statistically significant, we proceeded with a t-test with the follwing hypothesis:

H0 = average_total_duration_test_group <= average_total_duration_control_group;
H1 = average_total_duration_test_group > average_total_duration_control_group

The null hypothesis is rejected. The control group spends less total time on average than the test group.

### Experiment Evaluation

### Design Effectiveness
Clients were equally divided between the old and new designs. Characteristics like gender, tenure, accounts balance, online logs and calls were proportionally represented in both experiment groups.

### Duration Assessment
The experiment was done over a short time period, hence, the error rates and completion is high, not specifically because of the new UI being less effective, but because it always takes time to get comfortable with a new interface.

### Conclusion
From a statistical perspective: The new design improves user completion rates, which is a positive indicator for user engagement.

From a business perspective: The increase in completion rate is substantial and exceeds the pre-defined threshold of 5%. This is a critical factor for operational decision-making, as it suggests that scaling this solution will likely provide measurable benefits without overspending.

### Next Steps
Roll Out the New Design to a Larger Audience 
Calculate Long-Term Impact on financial metrics to see the long-term return on investment from the design change
Evaluate Scalability: check if this new design can be scaled across different customer segments 


### Tableau link
https://public.tableau.com/app/profile/lucie.stenger/viz/Ironhack-W5-6/KPIs?publish=yes 
