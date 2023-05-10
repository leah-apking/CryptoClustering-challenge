# CryptoClustering-challenge

The Crypto Clustering challenge uses unsupervised machine learning to if cryptocurrencies are affected by 24-hour or 7-day  price change percentages using the provided crypto_market_data.csv file. After loading our data into a Pandas DataFrame I used the StandardScalar module to normalize the data.

### Clustering the Original Scaled Data with KMeans

Using the elbow method to compare k-values to the inertia I determined that k=4 was the best k-value for this dataset. I then initialized and fit the KMeans model using the original scaled DataFrame and predicted the clusters. I then created a DataFrame with a copy of the scaled DataFrame and a column indicating the clusters predicted by the KMeans model. I used this to create an hvPlot scatter plot showing the 24-hour price change percentage and the 7-day price change percentage, coloring the plot points with the clusters indicated using KMean and including the crypto coin’s name in the hover information.

### Optimize Clusters with Principal Component Analysis

Using the original scaled DataFrame I created and fit the PCA model reducing the features to three principal components. I then retrieved the explained variance ratio which indicated that 89.5 percent of the total variance was explained by the three principal components. Next I created a new DataFrame containing the values determined by the model for PCA1, PCA2, and PCA3 of each crypto coin. I then repeated the elbow method, which again provided a value of k=4, and ran KMeans model for the PCA DataFrame and created another scatterplot showing the KMeans clusters. The PCA dataset KMeans model with k=4 returned the same clustering results as the original KMeans model using the scaled dataset; the clustering results were not impacted by using fewer features.
