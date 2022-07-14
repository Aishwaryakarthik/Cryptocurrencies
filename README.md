# Cryptocurrencies

# Overview of Project

You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

## Deliverables:

This new assignment consists of three technical analysis deliverables and a written report.

1.Deliverable 1: Preprocessing the Data for PCA

2.Deliverable 2: Reducing Data Dimensions Using PCA

3.Deliverable 3: Clustering Cryptocurrencies Using K-means

4.Deliverable 4: Visualizing Cryptocurrencies Results


## Unsupervised Machine Learning and Cryptocurrencies

Using Unsupervised Learning to Discover Unknown Patterns

Challenges of Unsupervised Learning

Unsupervised learning isn't the solution for every data analytic challenge. Just because supervised learning might not work for one situation doesn't mean unsupervised learning will work instead. Understanding the data and what can be done with it is an important first step before choosing an algorithm.

Recall that unsupervised learning does not take in any pairing of input and outcomes from the data—it only looks at the data as a whole. This can cause some challenges when running the algorithm. Since we won't know the outcome it's predicting, we might not know that the result is correct.

This can lead to issues where we're trying to decide if the model has provided any helpful information that we can use to make decisions in the real world. For example, our store owner might run a model that ends up grouping the type of people by how much they're buying. This could be useful in some contexts—for example, knowing who the top spenders are—but it might not help the store owner better organize the store for maximum purchases per person, or understand the differences in product preferences between top purchasers.

The only way to determine what an unsupervised algorithm did with the data is to go through it manually or create visualizations. Since there will be a manual aspect, unsupervised learning is great for when you want to explore the data. Sometimes you'll use the information provided to you by the unsupervised algorithm to transition to a more targeted, supervised model.

As with supervised learning, data should be preprocessed into a correct format with only numerical values, null value determination, and so forth. The only difference is unsupervised learning doesn't have a target variable—it only has input features that will be used to find patterns in the data. It's important to carefully select features that could help to find those patterns or create groups.

The next section will cover data preprocessing and data munging, and provide a refresher on Pandas and data cleaning. First, you'll need to install the necessary libraries for practice.

# Deliverable 1:

## Preprocessing the Data for PCA

### Deliverable Requirements:

Using your knowledge of Pandas, you’ll preprocess the dataset in order to perform PCA in Deliverable 2

#### Follow the instructions below:

Follow the instructions below and use the crypto_clustering_starter_code.ipynb file to complete Deliverable 1.

1.Open the crypto_clustering_starter_code.ipynb file, rename it crypto_clustering.ipynb, and save it to your Cryptocurrencies GitHub folder.

2.Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.

3.NOTE The crypto_data.csv was retrieved from CryptoCompare.

4.Keep all the cryptocurrencies that are being traded.

5.Keep all the cryptocurrencies that have a working algorithm.

6.Drop the IsTrading column.

7.Remove rows that have at least one null value.

8.Filter the crypto_df DataFrame so it only has rows where coins have been mined.

9.Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.

10.Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.

11.Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.

12.Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.


Take a moment to check that your crypto_df DataFrame looks like the image below:
<img width="635" alt="crypto_df_deliverable 1" src="https://user-images.githubusercontent.com/99555513/179049665-88d67800-541c-4437-b3f0-a40847f50438.png">

## Deliverable 2:

### Reducing Data Dimensions Using PCA

### Deliverable Requirements:

Using your knowledge of how to apply the Principal Component Analysis (PCA) algorithm, you’ll reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame.

#### Follow the instructions below:

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 2.

Continue using the crypto_clustering.ipynb file from Deliverable 1 where you’ve already performed the preprocessing steps.
Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.
If you’d like a hint on how to use the PCA algorithm, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.
Your DataFrame should look like the image below:

<img width="370" alt="deliverable_2_mod18" src="https://user-images.githubusercontent.com/99555513/179050159-dc85b11a-2652-4188-86cd-28a66c31611b.png">

## Deliverable 3:

### Clustering Cryptocurrencies Using K-means

#### Deliverable Requirements:

Using your knowledge of the K-means algorithm, you’ll create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, you’ll run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

#### Follow the instructions below:

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 3.

1.Continue using the crypto_clustering.ipynb file that you used in Deliverable 2 to reduce the dataset to three dimensions.

2.Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.

3.Next, use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data. If you’d like a hint on how to use the K-means algorithm, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

4.Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.

5.Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.

6.Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.

Your clustered_df DataFrame should look like the image below:
<img width="701" alt="clustered_df_mod 18" src="https://user-images.githubusercontent.com/99555513/179051511-5f40a309-9cf9-46b7-b7ed-5b74b5b8307b.png">

## Deliverable 4:

### Visualizing Cryptocurrencies Results

#### Deliverable Requirements:

Using your knowledge of creating scatter plots with Plotly Express and hvplot, you’ll visualize the distinct groups that correspond to the three principal components you created in Deliverable 2, then you’ll create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.

#### Follow the instructions below:

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 4.

1.Continue using the crypto_clustering.ipynb file from Deliverable 3 where you have predicted the K clusters for the cryptocurrencies’ data.

2.Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.

3.Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.

4.If you’d like a hint on how to add additional parameters to a Plotly Express 3D scatter plot, that’s totally okay. If not, that’s great too. You can always revisit this later if you change your mind.

5.Create a table with tradable cryptocurrencies using the hvplot.table() function.

Your table should look like the table in the image below:
<img width="458" alt="new_clustered_df_mod18" src="https://user-images.githubusercontent.com/99555513/179051918-faa91600-fd90-4c36-9e9f-91937e09c99f.png">
<img width="655" alt="hvplot" src="https://user-images.githubusercontent.com/99555513/179052535-4ff7b576-df31-4558-bd06-a74bf05dab39.png">




