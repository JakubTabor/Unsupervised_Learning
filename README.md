# [1. Clustering: Marketing campain](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Unsupervised_Clustering%20(1).ipynb)
# Our goal is to group unstructured data according to its similarities and patterns.
* To reach it we need to apply some techniques
# dimensionality reductions:

# Clustering:
* We can describe it as grouping similar informations
* Groups are created based of their common features

# First, we change the structure of my data to make it better self-descriptive
* Then I make simple outliers cleaning from outliers with help of graph plot
* Next I built correlation

# I take care of Categorical features with help of LabelEncoder and I drop features on deals
* Then use StandardScaler to scale all of my data

# I use PCA for dimensionality reduction and left only 3 the most important features
* I plot my dimensionality reduced data on 3D graph

# Next use elbow method to figure out optimal number of clusters
* And I use Agglomerative Clustering to create those clusters, then plot their distribution on 3D graph

# Then I check distribution of my clusters and go into details into customers profiling
* I use different plots to extract deeper sense of the informations about customer included in each cluster
* And figure out the best group of customers

#
#
#
# [2. Clustering: Online_Retail](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Online_Retail_PCA_Clustering.ipynb)
# In this part i gonna work on dataset which contain online shopping records

# First i do preprocessing of the data, which at this point is not ready to work on it
* I use a code to first check the percentage of missing values in dataset and next remove them

# Next using the current columns i gonna create new, which are gonna be more descriptive
* They are: **Amount, Frequency and Recency** and they become my new dataset

# Then i want to remove the outliers from my dataset
* First to take a look at my data distribution i plot my data on graph
* And next i use IQR tehnique to remove outliers
* Thanks to the previous graph i know where lie the outliers and i can define fences to exclude the highest and the lowest values

# Now when my data is in a fine range i can scale it and put into DataFrame
* Our dataset is now ready, we can check the description and see that everything is in fine range

# Next we are gonna build model for our dataset, it will be KMeans model 
