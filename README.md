# NETWORK-TD-SOM-Network and SOM of document topics
##### Case study: Master’s theses from NOVA IMS
 
## ABSTRACT
Digital libraries are innovative technologies for knowledge sharing. Endless quantities of documents/information are accessed through them. However, the efficiency of documents/information search systems and their ability to identify the desired and related information are not keeping pace with the ever-increasing volume of stored data. Here we present Network TD-SOM, a systematic process that offers a practical method of searching, visualising, organising, discovering related documents, and extracting knowledge from a vast corpus. It combines different topic modelling algorithms implemented separately with a two-level hybrid clustering approach and network analysis. In each technique, we exploit the results to design various kinds of spatialisation dedicated to different purposes. For example, some allow the uncovering of the thematic structure distribution over time and profiling of the clusters in a corpus. The main visualisation is an interactive corpus network that supports exploration, browsing, navigation, and zoom. Additionally, it allows incorporating the main results of each technique used and the useful metadata information into the visualisation. We evaluated the Network TD-SOM performance on the Master’s theses dataset from NOVA IMS. LDA and BERTopic successfully uncovered the thematic structure and extracted helpful knowledge of the dataset. However, BERTopic demonstrated superiority as a solution. The features/topics extracted from BERTopic also leverage the cluster results compared with the features from LDA. The arrangement of the two network theses had similarities with the cluster results. However, the one modelled by using features/topics from LDA was better than the BERTopic.

 
##### KEYWORDS: 
Corpus; Visualisation; Topic modelling; Clustering; Network



## Some results and visualisations

#### EXPLORATORY DATA ANALYSIS
##### Theses descriptive statistics
The theses from NOVA IMS Master programs can be considered as: a dissertation, an internship report or a work project. The dissertation has been the most preferred choice by students about to complete their masters.


![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/Distribution%20of%20the%20Master%20theses%E2%80%99%20type%20per%20year.png)

##### Abstract descriptive statistics
Figure below shows the distribution of the word numbers in the abstracts related to each thesis and the annual average of the word numbers. Overall, the number of words follows a normal distribution. Most abstracts have a total number of words within the expected range (around 80-250). 

![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/Distribution%20of%20word%20count%20and%20the%20annual%20average%20length%20of%20abstracts%20from%20theses.png)

Figure 6.5 illustrates the most popular 200 words in the abstracts. Overall, "Model", "data", "result", "area", "analysis", "system", "based", "project", "information", "study", "land_cover", "algorithm", "management" and "application knowledge" are some examples of words that are more frequently mentioned in the abstracts of the Masters' theses from NOVA IMS. 



#### TOPIC MODELLING RESULTS 
####### LDA results 
Figure below allows uncovering the thematic structure of the Master’s theses dataset and shows the average prevalence of the topics for four different courses/specialisations in a given year. Overall, in each course/specialisation, there is a good match with the respective most dominant topic. This indicates that LDA has correctly discovered the latent topics in an unsupervised way. 

##### Graphic legend
![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/LDA%20topics%20legend.png)
![pdf](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/distribution%20of%20weight%20topics%20by%20courses%20specialisations%20per%20year%20(lda)_graph_1.png)

##### Links below provides information about other courses/specialisations. In each course/specialisation, there is good matching with the respective most dominant topic.:
https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/distribution%20of%20weight%20topics%20by%20courses%20specialisations%20per%20year%20(lda)_graph_2.pdf
https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/distribution%20of%20weight%20topics%20by%20courses%20specialisations%20per%20year%20(lda)_graph_3.pdf

##### BERTopic results

Figure below shows the average prevalence of the topics for four different courses/specialisations in a given year. Overall, it is possible to see that the courses/specialisations and their dominant topics match. Additionally, the top 25 words are semantically linked with the names of the courses/specialisations where they are dominant. This indicates that BERTopic has correctly and semantically discovered the latent topics in an unsupervised way.

##### Graphic legend
![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/BERTopic%20topics%20legend.png)

![pdf](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/distribution%20of%20weight%20topics%20by%20courses%20specialisations%20per%20year%20(bertopic)_graph_1.png)


##### Links below provides information about other courses/specialisations. In each course/specialisation, there is good matching with the respective most dominant topic.:
https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/distribution%20of%20weight%20topics%20by%20courses%20specialisations%20per%20year%20(bertopic)_graph_2.pdf
https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/distribution%20of%20weight%20topics%20by%20courses%20specialisations%20per%20year%20(bertopic)_graph_3.pdf


#### CLUSTERING RESULTS
A hybrid clustering approach was used to find the clusters of the theses. In the first stage, SOM was applied. The best match units (BMUs) found in the first stage, were used in the second stage. Ward was applied on the BMUs. After analysing the dendrogram, the solution of 6 and 5 clusters using the topic vectors/features from LDA and BERTopic were selected, respectively. Figure below shows how the clusters are organised using features from each topic modelling algorithm.

###### som heatmaps from lda topic vectors
![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/LDA%20topics%20legend.png)
###### som heatmaps from bertopic topic vectors
![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/LDA%20topics%20legend.png)

#### Network of the theses

##### The theses network results (LDA topic vector)
Figure bellow shows the interlinkages of the master theses from NOVA IMS modelled by using the LDA topic vectors. The arrangement of the network has a good similarity with cluster results. 

![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/The%20master%20theses%20network%20by%20using%20LDA%20topic%20vectors.png)


##### The theses network results (BERTopic topic vector)
Figure below shows the interlinkages of the master theses from NOVA IMS modelled by using the BERTopic topic vectors. Overall, the network is dense, and some nodes are overlapping. 

![image](https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/The%20master%20theses%20network%20by%20using%20BERTopic%20topic%20vectors.png)


