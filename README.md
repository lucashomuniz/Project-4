# ✅ PROJECT-4

In the fast-paced world of commercial aviation, on-time flights play a key role in passenger satisfaction and airline success. Given this scenario, an intriguing business problem arises: do the flights of a certain airline have a longer history of delays than the flights of another airline? To answer this question, a hypothesis test was developed that allows us to assess whether there are significant differences between the two airlines with regard to the punctuality of their flights.

Delta Airlines and United Airlines are two of the industry's leading airlines, known for their global reach and serving millions of passengers each year. However, each one has its own operations and particularities that can influence the punctuality of its flights. By performing a well-structured hypothesis test, we will be able to gain a clearer view of each airline's performance and its ability to meet schedules.

The purpose of this hypothesis test is to provide valuable insights for both companies, helping them to identify patterns and trends regarding flight delays. By examining the historical data of the two companies (Dataset Flights), we will be able to compare the proportion of delayed flights between Delta Airlines and United Airlines, seeking to establish whether there is a statistically significant difference between them. Based on this analysis, airlines will be able to take appropriate measures to improve operational efficiency and the passenger experience, if necessary.

Keywords: R Language, Data Analysis, Flights Library, Data Visualization, Historical, Statistical Models, Students t-test, p-value

# ✅ PROCESS

Let's take a step-by-step analysis of United Airlines (UA) and Delta Airlines (DL) flight data and draw conclusions based on the available information. First, we create a dataset called pop_data using the Flights library. This dataset contains information about airlines UA and DL, with a focus on delays in arriving flights. It has two columns, one for the company name and one for the delay. Then, we split the dataset into two samples, each containing 1000 observations. Sample 1 represents data from Delta Airlines (DL), while sample 2 represents data from United Airlines (UA). This division will allow us to separately analyze the performance of each company. With the samples separated, we reassembled the data into a single dataset, to facilitate comparison.

We sequentially calculated the confidence interval (95%) for each sample. This range gives us a range of values around the mean, where the true population mean is likely to be. We used the sample mean standard deviation formula and a reference value (1.96) to find the lower and upper limits of the confidence interval. When analyzing the results, we see that sample 1 (Delta Airlines) has an average flight delay of approximately 39,299, with a confidence interval ranging from approximately 34.66 to 43.93. This means that the average delay is completely within this range. Similarly, sample 2 (United Airlines) has a mean flight delay of about 34.33, with an approximate confidence interval of 31.34 to 37.33. Again, the mean is within this range.

We visualize the confidence intervals in a graph, which helps us to compare the samples more clearly. Based on these data, we conclude that the samples probably come from the same population, as most of the values are within the same confidence intervals. Then, we proceed to a comparison analysis between the companies. We do a hypothesis test to see if Delta Airlines (DL) flights are delayed longer than United Airlines (UA) flights.

We established the Null Hypothesis (H0), which says that there is no significant difference between the delays of the two companies, that is, the difference in the average delays is equal to zero. The Alternative Hypothesis (HA) is that DL flights are more delayed, with a positive difference in average delays. Using the t-test and calculating the p-value, we come to the conclusion that we failed to reject the null hypothesis. The p-value is greater than the 0.05 significance level, which means that there is a high probability that there is no significant difference between the companies' delays.

# ✅ CONCLUSION

Based on the analyzed data, we have no statistical evidence to state that (DL) delays more than (UA). Thus, considering all the steps and analyzes performed, we can conclude that the samples probably come from the same population and there is no statistical evidence that Delta Airlines performs worse in relation to flight delays when compared to United Airlines.
