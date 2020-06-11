### Part 2 ‑ Experiment and metrics design

The neighboring cities of Gotham and Metropolis have complementary circadian rhythms: on
weekdays, Ultimate Gotham is most active at night, and Ultimate Metropolis is most active
during the day. On weekends, there is reasonable activity in both cities.
However, a toll bridge, with a two way toll, between the two cities causes driver partners to tend
to be exclusive to each city. The Ultimate managers of city operations for the two cities have
proposed an experiment to encourage driver partners to be available in both cities, by
reimbursing all toll costs.

1. What would you choose as the key measure of success of this experiment in
encouraging driver partners to serve both cities, and why would you choose this metric?
2. Describe a practical experiment you would design to compare the effectiveness of the
proposed change in relation to the key measure of success. Please provide details on:
a. how you will implement the experiment
b. what statistical test(s) you will conduct to verify the significance of the
observation
c. how you would interpret the results and provide recommendations to the city
operations team along with any caveats.

### 1.
We need a metric which will be at a maximum when the driver has the same number of pickups in both cities and at a minimum when when all pickups are in one city or the other. Desirable properties for this metric are:

1. It is linear over the domain
2. It has a maximum value of 1 when the number of pickups are the same in both cities
3. It has a value of zero when all pickups are in one city or the other

A good candidate metric for this situation is

    score = 1 - abs(G^2 - M^2)
    
Where G is the fraction of pickups in Gotham for a given driver and M is the fraction of pickups in Metropolis for a given driver. This metric results in a an inverted V shaped curve which has a maximum at of 1 when the fraction of pickups in Metropolis and Gotham are 0.5.

### 2.
a. The experimental design for this trial will be a simple repeated measures design. I assume that much data for the 'no treatment', i.e. no toll reimbursement is already available. Therefore all that would be needed is to start a pilot program where a small number of drivers are reimbursed for tolls. Without a beforehand idea of the expected effect size it is hard to estimate the necessary sample size to achieve statistical power. An initial cohort of at least 30 drivers would be required and the more the better. This could be dictated in part by the available funding for the pilot reimbursement program.

b. The statistical analysis of this experiment will be simple. Our score metric will be calculated for each driver enrolled in the program before and after the reimbursement began. Then a simple one tailed t-test for matched pairs would be conducted against the null hypothesis that the mean of the difference in scores is zero.

c. The interpretation of this experiment would be simple. The null hypothesis could be accepted or rejected based on the p-value calculated from the t-test. The major caveat in interpretation would be the fact that a statistically significant result is not always an important result. This experiment could prove that any effect observed in the pickup distribution between cities is not due to chance. However, it cannot tell us if the toll reimbursement program is a good idea. To determine that, we would have to look at other factors - total number of trips, length of trips, driver/passenger satisfaction etc.