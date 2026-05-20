# lab11_machinelearning
This lab applies K-Means clustering to a credit card customer dataset. The goal is to group customers based on their spending behaviour, balance, purchases, cash advance usage, credit limit, payments, and other financial features.

The dataset was first cleaned by removing the customer ID column and filling missing values using the mean. Then, the features were scaled using StandardScaler because K-Means depends on distance. The elbow method and silhouette score were used to help choose the number of clusters.

The final model used K = 4 clusters. The clusters helped identify different customer segments, such as high-value customers, low-activity customers, regular purchase customers, and customers who rely more on cash advances.


## Final Questions:

1. Why is this an unsupervised learning problem?

Answer: This is an unsupervised learning problem because the dataset does not have a target label or correct answer column. We are not predicting a known class. Instead, K-Means finds patterns in the customer data and groups similar customers into clusters.
-
2. Why did we remove the CUST_ID column?

Answer: We removed the CUST_ID column because it is only an identifier for each customer. It does not describe customer behaviour, so it does not help K-Means create meaningful clusters.
-
3. Which columns had missing values?

Answer: The columns with missing values were CREDIT_LIMIT and MINIMUM_PAYMENTS.
-
4. How did you handle the missing values?

Answer: I handled the missing values by filling them with the mean value of each column. This keeps the rows in the dataset and avoids errors when applying scaling and K-Means.
-
5. Why is scaling important before applying K-Means?

Answer: Scaling is important because K-Means uses distance to group data points. If the features have different ranges, columns with large values, such as BALANCE, PURCHASES, or CREDIT_LIMIT, can dominate the clustering. Scaling makes all features more balanced.
-
6. Which K value did you choose? Explain your answer using the elbow method and silhouette score.

Answer: I chose K = 4. The elbow method showed that the inertia starts decreasing more slowly around 4 clusters, which means 4 is a reasonable number of clusters. The silhouette score was highest at K = 3, but K = 4 still gave useful and more detailed customer segments, so I used 4 clusters for the final model.
-
7. Based on the cluster summary table, describe each customer segment in your own words.

Answer:
Cluster 0 represents customers with moderate purchases, low cash advance usage, and regular purchase activity. These customers use their credit cards mainly for purchases and installment payments.
Cluster 1 represents high-spending customers. They have very high purchases, high one-off purchases, high credit limits, and high payments. This group looks like the most valuable customer segment.
Cluster 2 represents customers with high balances and very high cash advance usage. They make fewer purchases but rely heavily on cash advances.
Cluster 3 represents low-activity customers. They have low purchases, low purchase frequency, lower payments, and generally use their credit cards less than the other groups.
-
8. Which cluster may represent high-value customers?

Answer: Cluster 1 may represent high-value customers because they have the highest purchases, high credit limits, high payments, and very frequent purchasing behaviour.
-
9. Which cluster may represent customers who rely more on cash advance?

Answer: Cluster 2 may represent customers who rely more on cash advances because it has the highest CASH_ADVANCE, CASH_ADVANCE_FREQUENCY, and CASH_ADVANCE_TRX.
-
10. How can a company use these clusters for marketing strategy?

Answer: A company can use these clusters to create different marketing strategies for each customer group. High-value customers can receive premium offers, rewards, and loyalty programs. Customers who use cash advances often can receive financial planning offers or lower-interest cash advance promotions. Low-activity customers can receive discounts or campaigns to encourage more card usage. Regular purchase customers can receive cashback, installment offers, or shopping rewards.
