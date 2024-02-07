# [1. Clustering: Marketing campain](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Unsupervised_Clustering%20(1).ipynb)
# Our goal is to group unstructured data according to its similarities and patterns.
* To reach it we need to apply some techniques
# dimensionality reductions:

# Clustering:
* We can describe it as grouping similar informations
* Groups are created based of their common features

# First, we change the structure of my data to make it better self-descriptive
# [Data preprocessing and feature engineering](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Description/marketing_campaign_preprocess_desc)
* Then I make simple outliers cleaning from outliers with help of graph plot
* Next I built correlation

# I take care of Categorical features with help of LabelEncoder and I drop features on deals
* Then use StandardScaler to scale all of my data

# I use PCA for dimensionality reduction and left only 3 the most important features
# [Dimensionality reduction and model evaluation](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Description/market_campain_dim_reduction_desc)
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
# [Preprocessing and feature engineering](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Description/Online_retail_preprocess_desc)
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
# [Clustering and model evaluation](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Description/Online_retail_clustering_model_eval_desc)
* But first we are gonna figure our number of clusters from our dataset
* First we check it using inertia_ and supplying 7 possible num. of clusters
* Next we use Silhouette Score and overall from this 2 techniques we see that the best num. of clusters is 3
* And sign kmeans labels to our dataset, thats how we reach its final form

# Now we can check on graph the characteristics of each cluster
* And we derive following conclusions:

# We also check the hierarhical clustering, and it gives us similar conclusions
* Numbers are different, but still the order is the same

# And that's the final summary of each 3 clusters:
# And we can say that the Cluster nr. 3 is the most important in sence of customers
# And Cluster nr. 2 is little below
# The Cluster nr. 1 at the last place

#
#
#
# [3. PCA: Face Recognition](https://github.com/JakubTabor/Unsupervised_Learning/blob/main/Face_Recognition_Pipeline.ipynb)
# In this part i gonna build a model for face recognition, based on face dataset, which i include in CSV directory
# [CSV directory](https://github.com/JakubTabor/Unsupervised_Learning/tree/main/CSV)
# First i start from data exploration 
* To do this i create function with plt module
* And to check data properties i use prints of por example: number of target and image size

# Then i come to the part of data preparation
* It contains input reshaping, then data splitting, but always i follow how changes shapes and check if i have class balance

# Next i come to the part of PCA, i use the graph for visual explanation
