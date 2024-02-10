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
* To do this i use mglearn module and then plt function, to represent it on my dataset

# Then i gonna figure our out the optimal number of clusters
* First i use KElbow technique, i run it for many iterations and only few iterations, but i dont get any concrete results
* So i try another technique, which is graph of variance explanation, a now i can see that variance stabilize around 50 - 90 components
* I stay with maximum allowed - 90, i pass to my PCA model 90 components and train it on my dataset
* Then i plot on graph the average face from my model and the eigenfaces, so the components of my model

# Now i can come to the part of classification
* I start from transforming X_train and X_test
* Next i couple models and and train them, the best scores reach LinearDiscriminant, LogisticRegression and SVC

# Next i do further evaluations to reach the clarity which model is the best, so i use cross validation score
* I supply the KFold model with 5 splits of data and shuffling parameter
* And i put it into cross_val_score model, as well as all my models and my data and targets
* 2 model achieve the best accuracy: LinearDiscriminant and LogisticRegression

# Another measurement that i do is by LeaveOneOut model, it leave only 1 sample for evaluation
* I supply into cross_val_score model both classifiers, then X and y, then LeaveOneOut model
* And LinearDiscrimiant have little better score and it will be my finall model
 
# Now i gonna show precision and recall curves and measure micro average score over all classes using my LD model 
* I gonna do multiclass classification using OneVsRestClassifier
* First i prepare my data, by binarizing my labels and creating train and test multiclass sets
* Then transforming them using PCA, then training OneVsRestClassifier and get y_score
* Now i can create dictionaries for precision recall and average_precision and fill them for each classes
* Then take average and micro-average and i achieve score: 0.95 
* And i plot precision and recall with plt and signature

# And finally i also arrange the operations in Piepeline
* I supply my 2 best models into workflow and then train them, next get predictions
