# p8105_hw5_hj2660

Problem 1
The Washington Post has gathered data on homicides in 50 large U.S. cities and made the data available through a GitHub repository here. You can read their accompanying article here.

Describe the raw data. Create a city_state variable (e.g. “Baltimore, MD”) and then summarize within cities to obtain the total number of homicides and the number of unsolved homicides (those for which the disposition is “Closed without arrest” or “Open/No arrest”).

For the city of Baltimore, MD, use the prop.test function to estimate the proportion of homicides that are unsolved; save the output of prop.test as an R object, apply the broom::tidy to this object and pull the estimated proportion and confidence intervals from the resulting tidy dataframe.

Now run prop.test for each of the cities in your dataset, and extract both the proportion of unsolved homicides and the confidence interval for each. Do this within a “tidy” pipeline, making use of purrr::map, purrr::map2, list columns and unnest as necessary to create a tidy dataframe with estimated proportions and CIs for each city.

Create a plot that shows the estimates and CIs for each city – check out geom_errorbar for a way to add error bars based on the upper and lower limits. Organize cities according to the proportion of unsolved homicides.

Problem 2
This zip file contains data from a longitudinal study that included a control arm and an experimental arm. Data for each participant is included in a separate file, and file names include the subject ID and arm.

Create a tidy dataframe containing data from all participants, including the subject ID, arm, and observations over time:

Start with a dataframe containing all file names; the list.files function will help
Iterate over file names and read in data for each subject using purrr::map and saving the result as a new variable in the dataframe
Tidy the result; manipulate file names to include control arm and subject ID, make sure weekly observations are “tidy”, and do any other tidying that’s necessary
Make a spaghetti plot showing observations on each subject over time, and comment on differences between groups.

Problem 3
When designing an experiment or analysis, a common question is whether it is likely that a true effect will be detected – put differently, whether a false null hypothesis will be rejected. The probability that a false null hypothesis is rejected is referred to as power, and it depends on several factors, including: the sample size; the effect size; and the error variance. In this problem, you will conduct a simulation to explore power in a one-sample t-test.

First set the following design elements:

Fix n=30
Fix σ=5
Set μ=0
. Generate 5000 datasets from the model

x∼Normal[μ,σ]

For each dataset, save μ̂ 
 and the p-value arising from a test of H:μ=0
 using α=0.05
. Hint: to obtain the estimate and p-value, use broom::tidy to clean the output of t.test.

Repeat the above for μ={1,2,3,4,5,6}
, and complete the following:

Make a plot showing the proportion of times the null was rejected (the power of the test) on the y axis and the true value of μ
 on the x axis. Describe the association between effect size and power.
Make a plot showing the average estimate of μ̂ 
 on the y axis and the true value of μ
 on the x axis. Make a second plot (or overlay on the first) the average estimate of μ̂ 
 only in samples for which the null was rejected on the y axis and the true value of μ
 on the x axis. Is the sample average of μ̂ 
 across tests for which the null is rejected approximately equal to the true value of μ
? Why or why not?
