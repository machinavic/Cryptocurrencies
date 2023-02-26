# Cryptocurrencies
## Purpose
The purpose of this repo is working on Unsupervised Machine Learning models aplplied in this case the Cryptocurrencies field.

Mainly, the project was split into fourth (4) parts depicted here below:

###*Part 1: Preprocessing the Data for PCA.
On the crypto_df DataFrame, all cryptocurrencies that were not being traded were removed, one column named "IsTrading" was dropped,
the rwos with "NaN" values were removed as well the rows that did not have coins being mined were removed too.

A new DataFrame was created that stored all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame.
The get_dummies() method was used to create variables for the text features, which are then stored in a new DataFrame, "X" and the features from the X DataFrame have been standardized using the StandardScaler fit_transform() function.

###*Part 2: Reducing Data Dimensions Using PCA.

The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components, and the pcs_df DataFrame was created and has the following three columns: PC 1, PC 2, and PC 3.
Besides it has the index from the crypto_df DataFrame.

###*Part 3: Clustering Cryptocurrencies Using K-means.
The K-means algorithm was used to cluster the cryptocurrencies using the PCA data, where an elbow curve was created using hvPlot to find the best value for K,
and predictions were made on the K clusters of the cryptocurrencies’ data.

A new DataFrame was created with the same index as the crypto_df DataFrame and had the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class.

###*Part 4: Visualizing Cryptocurrencies Results

The clusters were plotted using a 3D scatter plot, and each data point showing the CoinName and Algorithm on hover.
A table with tradable cryptocurrencies was created using the hvplot.table() function, and the total number of tradable cryptocurrencies was printed.
as well, a DataFrame was created containing the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns.
Lastly but not least, a hvplot scatter plot was created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data ordered by "Class",
and it shows the CoinName when you hover over the data point (10 points)