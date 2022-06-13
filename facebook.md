###### Social network Graph Link Prediction - Facebook Challenge

###### Problem statement:
Given a directed social graph, have to predict missing links to recommend users (Link Prediction in graph)

###### Data Overview
Taken data from facebook's recruting challenge on kaggle https://www.kaggle.com/c/FacebookRecruiting
data contains two columns source and destination eac edge in graph - Data columns (total 2 columns):
- source_node int64
- destination_node int64

###### Mapping the problem into supervised learning problem:
Generated training samples of good and bad links from given directed graph and for each link got some features like no of followers, is he followed back, page rank, katz score, adar index, some svd fetures of adj matrix, some weight features etc. and trained ml model based on these features to predict link.
Some reference papers and videos :
https://www.cs.cornell.edu/home/kleinber/link-pred.pdf
https://www3.nd.edu/~dial/publications/lichtenwalter2010new.pdf
https://kaggle2.blob.core.windows.net/forum-message-attachments/2594/supervised_link_prediction.pdf
https://www.youtube.com/watch?v=2M77Hgy17cg

###### Business objectives and constraints:
No low-latency requirement.
Probability of prediction is useful to recommend ighest probability links

###### Performance metric for supervised learning:
Both precision and recall is important so F1 score is good choice
Confusion matrix

###### 1) Initially we have only a couple feature in our data-set. First we performed exploratory data analysis on our given data set such as number of followers and followees of each person.

2) Then after we generated some datapoints which were not present in our given data-set, since we had only class label 1 data.

3) Then we did some feature engineering on dataset like finding shortest path, kartz centrality, jaccard distances, page rank, preferential attachements etc.

4) After performing eploratory data analysis and feature engineering we splitted whole dataset into train and test and performed random forest and xgboost taking f1-score as our metric.

5) At the end we plotted confusion matrix and pretty-table for both algorithm and found best hyperparameters.
