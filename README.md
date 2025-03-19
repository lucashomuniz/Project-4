# ✅ PROJECT-04

This project was developed for a multinational company in the industrial sector that produces snacks, biscuits, and chocolates. Due to the complexity of its production process, the company needs to continuously monitor the work of planners, who compare commercial volumes with the forecasts generated by the data team. The main objective was to create an analytical solution to compare the historical volumes of different products with the forecasts for the following year, which were calculated using machine learning algorithms.  

The analysis considered three categories: base volume, volume during exclusively promotional periods, and total volume. To ensure the reliability of the forecasts, a statistical methodology based on Confidence Intervals was developed, allowing the construction of statistical variables that assisted in calculating the upper and lower limits. This approach enabled the evaluation of not only the proximity between historical and forecasted values but also whether the forecasts fall within a statistically acceptable range, providing greater security for planners.  

The data was extracted directly from the Data Warehouse in the Google Cloud Platform via Direct Query for Power BI, using SQL for selection, transformation, and cleansing of the dataset, which contains more than 2 million rows. In addition to supporting decision-making processes, the solution also allows the data team to assess the accuracy of the machine learning model used for volume forecasting, ensuring the optimization of results and enhancing reliability in decision-making.

**Keywords**: Data Analysis, Statistical Analysis, Confidence Intervals, Google Cloud Plataform, BigQuery, PowerBI, PowerQuery, DAX

# ✅ PROCESS

The analytical solution was developed using the DAX language to calculate key statistical variables essential for defining the confidence interval, enabling a robust evaluation of data predictability. The first step involved calculating the moving average, which is crucial for smoothing seasonal fluctuations and identifying sales volume trends over time. Next, the moving standard deviation was determined to measure data dispersion relative to the mean, providing an estimate of weekly sales variability.  

With these parameters, the upper and lower confidence interval limits were established, defined as 1.645 times the moving standard deviation—a statistical criterion corresponding to an approximately 90% confidence level. This threshold was pre-determined for the project to ensure a balance between sensitivity and robustness in detecting atypical variations. Finally, the number of outliers over the weeks of the year was calculated, identifying periods when forecast values exceeded the confidence interval limits. This analysis is crucial for detecting potential distortions in predictive models and adjusting operational strategies accordingly.  

![Screen Recording 2025-03-19 at 12 19 44](https://github.com/user-attachments/assets/73164cb9-54d3-4415-9cda-135ba7795383)

The dashboard interface was designed to be intuitive and centralized on a single page, ensuring ease of use and interpretation of results. At the top, users can apply filters to select material, customer, product family (PPG), and weekly period, enabling segmented and specific analyses. The main panel features a dynamic line chart, which can be adjusted according to three key parameters: Variables, Interval, and Outliers. Users can switch between different categories of historical and forecasted data, separating them by product type (base, promotional, or total) and analyzing trends in detail.  

At the bottom of the dashboard, a data matrix summarizes the weekly values of key metrics, providing a consolidated view of historical and projected quantities and values. With this structure, the solution enables an in-depth statistical analysis of demand and predictive performance, supporting data-driven strategic decision-making.

# ✅ CONCLUSION

The analytical solution developed in this project enabled a detailed assessment of the relationship between historical volumes and future forecasts, ensuring greater reliability in decision-making. The application of confidence intervals facilitated a robust statistical analysis, allowing the identification of patterns, atypical variations, and the accuracy of predictive models. As a result, the planning team can make more informed decisions, reducing uncertainties and optimizing demand management. This approach strengthens the company’s analytical and strategic capabilities, improving not only the planning process but also the continuous calibration of machine learning models, ensuring increasingly accurate forecasts aligned with market realities.

**Dashboard**: https://app.powerbi.com/view?r=eyJrIjoiYjYxMWNmZDMtMDcxYy00YjIwLTliODgtMWRjMWNhYWY2YjRiIiwidCI6ImQ2OWE3NzgzLWU5MzctNDIzMi1iYTg1LTIwOTg0MDgzODJjOCJ9
