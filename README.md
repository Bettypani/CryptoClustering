# CryptoClustering Analysis

### Prepare the Data
- Normalize the data from the CSV file using StandardScaler().
- Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

### Find the Best Value for k Using the Original Scaled DataFrame
- Use the elbow method to find the best value for k.
  - Create a list with the number of k values from 1 to 11.
  - Create an empty list to store the inertia values.
  - Compute the inertia with each possible value of k.
  - Plot a line chart with all the inertia values computed to identify the optimal value for k.
- **Question**: What is the best value for k?

### Cluster Cryptocurrencies with K-means Using the Original Scaled Data
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the original scaled DataFrame.
- Predict the clusters to group the cryptocurrencies.
- Create a scatter plot using hvPlot.
  - Set the x-axis as "PC1" and the y-axis as "PC2".
  - Color the graph points with the labels found using K-means.
  - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### Optimize Clusters with Principal Component Analysis (PCA)
- Perform PCA on the original scaled DataFrame to reduce features to three principal components.
- Retrieve the explained variance for each principal component.
- **Question**: What is the total explained variance of the three principal components?
- Create a new DataFrame with the PCA data and set the "coin_id" index.

### Find the Best Value for k Using the PCA Data
- Use the elbow method on the PCA data to find the best value for k.
- Plot a line chart with inertia values to identify the optimal value for k.
- **Question**: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?

### Cluster Cryptocurrencies with K-means Using the PCA Data
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the PCA data.
- Predict the clusters to group the cryptocurrencies.
- Create a scatter plot using hvPlot.
  - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  - Color the graph points with the labels found using K-means.
  - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### Impact of Using Fewer Features
- **Question**: What is the impact of using fewer features to cluster the data using K-Means?
