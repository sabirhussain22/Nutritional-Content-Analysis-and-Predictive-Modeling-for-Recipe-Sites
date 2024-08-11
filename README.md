# Recipe Site Analysis and Findings
This report will provide a comprehensive analysis of the dataset, including data validation and cleaning steps for each column. Exploratory data analysis will show graphical representations of single and multiple variables. Which provides insights and findings in a summarized way. Then about model development from defining the problem type to fitting baseline and comparison models. Then how these models are evaluated. Finally, recommendations for the business will be presented that focus on predicting recipe popularity and traffic optimization on the website.
## Data Validation
For data validation and cleaning, our first step was handling missing values. In the high_traffic column, where traffic data was missing, we filled those entries with 'Low' to represent a new category. Additionally, in numerical columns like 'calories', 'carbohydrate', 'sugar', and 'protein', which had around 5.4% missing values, we replaced them with the mean of their respective columns to maintain data integrity.
Next, we encoded categorical columns to facilitate analysis. The high_traffic column was mapped to binary values: 'High' was assigned as 1 and 'Low' as 0, aiding in classification tasks. Similarly, for the 'category' column, we created a mapping dictionary, converting category names into integer values for computational efficiency.
Lastly, we addressed special cases to ensure consistency in the dataset. In the 'servings' column, where serving sizes were indicated as '4 as a snack' or '6 as a snack', we adjusted these values to 3 and 5, respectively. This was followed by converting the column to integers (int64) for uniformity and ease of analysis. These measures collectively prepared our dataset for subsequent analysis and modeling, enhancing its reliability and usability.
## Exploratory Analysis
### Histograms for Single Variables:
We utilized histogram plots to visualize the distribution of calories and protein content across recipes. These histograms revealed that most recipes tend to have relatively low levels of both calories and protein. Most recipes fell within specific ranges for these nutritional components, indicating a general balance in nutritional profiles across the dataset.


### Average Calorie Content Across Recipe Categories:
By plotting the average calorie content across different recipe categories, we gained insights into the relative nutritional density of recipes within each category. Our analysis revealed that pork-based recipes exhibited the highest average calorie content, while beverages had the lowest. These findings shed light on the varying nutritional profiles of different recipe categories, aiding in understanding dietary choices and preferences.
 
### Pair Plot Analysis of Nutritional Content by Category:
We generated a pair plot to explore relationships between protein, carbohydrates, sugar, and calories across various food categories. This visual representation allowed us to identify potential correlations and outliers in nutritional content. Notably, we observed a positive correlation between protein and calorie content, indicating that foods rich in protein tend to have higher calorie content. Additionally, categories like breakfast beverages demonstrated elevated levels of both sugar and carbohydrates, suggesting a significant contribution to overall carbohydrate intake from sugars in these beverages. However, the presence of outliers underscored variability within each category, emphasizing the need for further exploration and data validation to confirm these trends definitively.
 
## Model Development
This problem involves predicting recipe popularity.  Which falls under the category of classification tasks. Specifically, we aim to classify recipes into two categories: high-traffic and low-traffic, based on the high_traffic column in our dataset. This classification problem enables us to make predictions about recipe performance on the website.
### Fitting a Baseline Model:
To establish a baseline model for our predictive modeling, we used a simple logistic regression model. This baseline model provides a starting point for comparison with more complex algorithms. Logistic regression is a straightforward yet effective method for binary classification tasks, making it suitable for our initial modeling efforts.
### Fitting a Comparison Model:
In addition to the baseline logistic regression model, we fitted a more complex algorithm for comparison. I experimented with various models such as random forests, XG Boost, Gradient Boosting, and decision trees. These models offer higher complexity and potentially greater predictive power compared to logistic regression. By comparing the performance of these models against the baseline, I have identified that the Random Forest and Gradient Boosting are most suitable for our prediction task.
## Model Evaluation
The logistic regression model achieved an accuracy of 61.05%. It had a precision of approximately 59.60%, recall of 61.05%, and an F1 score of 49.35%.
 
On the other hand, the random forest model outperformed the logistic regression with an accuracy of 73.16%. It demonstrated a precision of around 72.91%, recall of 73.16%, and an F1 score of 72.98%.
 
Similarly, the gradient boosting model also surpassed the logistic regression, yielding an accuracy of 74.21%. It exhibited a precision of about 73.98%, recall of 74.21%, and an F1 score of 74.04%.
 
Overall, both the random forest and gradient boosting models outperformed the logistic regression model across all evaluation metrics.
Defining a metric for the business to monitor
## Metric Definition for Business Monitoring
To monitor the success of predicting recipe popularity, the business should track the accuracy of the prediction model. This metric reflects the percentage of correctly predicted high-traffic and low-traffic recipes, providing insights into the model's effectiveness in identifying popular recipes on the website.
Monitoring Approach:
The business can monitor the accuracy metric by regularly evaluating the model's predictions against actual website traffic data. This can be done on a weekly or monthly basis to assess the model's ongoing performance and identify any potential fluctuations or trends in recipe popularity.
Initial Value Estimation:
Based on our current data and model evaluations, we estimated the initial accuracy value to be approximately 74.21% for the Gradient Boosting model. This serves as a baseline for comparison and provides a starting point for tracking improvements in model performance over time.
 ## Conclusion
In conclusion, to improve recipe popularity prediction and enhance website traffic, we suggest ongoing model refinement, particularly focusing on Random Forest and Gradient Boosting algorithms. Additionally, exploring additional features for better prediction accuracy, implementing a robust monitoring system for continuous evaluation, and integrating user feedback mechanisms for personalized content recommendations are recommended. A/B testing experiments should be conducted to optimize website layout and recipe recommendations, facilitating data-driven decision-making. By adopting these strategies, the business can effectively predict and showcase popular recipes, leading to increased user engagement, higher traffic, and improved customer satisfaction.

