# vanguard-ab-test

Vanguard believed that a more intuitive and modern User Interface (UI), coupled with timely in-context prompts (cues, messages, hints, or instructions provided to users directly within the context of their current task or action), could make the online process smoother for clients. The critical question is: Would these changes encourage more clients to complete the process?

## An A/B test was set into motion from 3/15/2017 to 6/20/2017 by the team.
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
1. Completion Rate: The new design (Test group) has a higher completion rate compared to the old design (Control group). In order to confirm if this difference is statistically significant, we proceeded with a z-test.

2. Time Spent on Each Step: t-test

3. Error Rates: The new design (Test group) has a higher Error rate compared to the old design (Control group). In order to confirm if this difference is statistically significant, we proceeded with a z-test with the following hypothesis:
H0 = error rate test group <= error rate control group
H1 = error rate test group > error rate control group
The null hypothesis is rejected. The error rate in the test group is larger than the control group.


5. Time Spent from Start to Confirm Step (additional KPI):

