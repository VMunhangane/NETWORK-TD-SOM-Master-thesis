# NETWORK-TD-SOM-Network and SOM of document topics
##### Case study: Master’s theses from NOVA IMS
 
## ABSTRACT
Digital libraries are innovative technologies for knowledge sharing. Endless quantities of documents/information are accessed through them. However, the efficiency of documents/information search systems and their ability to identify the desired and related information are not keeping pace with the ever-increasing volume of stored data. Here we present Network TD-SOM, a systematic process that offers a practical method of searching, visualising, organising, discovering related documents, and extracting knowledge from a vast corpus. It combines different topic modelling algorithms implemented separately with a two-level hybrid clustering approach and network analysis. In each technique, we exploit the results to design various kinds of spatialisation dedicated to different purposes. For example, some allow the uncovering of the thematic structure distribution over time and profiling of the clusters in a corpus. The main visualisation is an interactive corpus network that supports exploration, browsing, navigation, and zoom. Additionally, it allows incorporating the main results of each technique used and the useful metadata information into the visualisation. We evaluated the Network TD-SOM performance on the Master’s theses dataset from NOVA IMS. LDA and BERTopic successfully uncovered the thematic structure and extracted helpful knowledge of the dataset. However, BERTopic demonstrated superiority as a solution. The features/topics extracted from BERTopic also leverage the cluster results compared with the features from LDA. The arrangement of the two network theses had similarities with the cluster results. However, the one modelled by using features/topics from LDA was better than the BERTopic.

 
##### KEYWORDS: 
Corpus; Visualisation; Topic modelling; Clustering; Network



## Some results and visualisations

#### EXPLORATORY DATA ANALYSIS
##### Theses descriptive statistics
The theses from NOVA IMS Master programs can be considered as: a dissertation, an internship report or a work project. Figure 6.1 summarises the numbers of each type of theses across the last two decades. Overall, the three types of theses show clear upward trends in numbers. However, they marginally decreased in 2021 for dissertations and work projects.  The dissertation has been the most preferred choice by students about to complete their masters. Although the Internship report is the least preferred choice, its number rose slightly to about forty (40) theses in 2021.

https://github.com/VMunhangane/NETWORK-TD-SOM-Master-thesis/blob/main/analysis/Distribution%20of%20the%20Master%20theses%E2%80%99%20type%20per%20year.png

##### Abstract descriptive statistics
Figure 6.3 shows the distribution of the word numbers in the abstracts related to each thesis and the annual average of the word numbers. Overall, the number of words follows a normal distribution. Most abstracts have a total number of words within the expected range (around 80-250). Consequently, the average in most of the years is below 250. 

### Adcionar Grafico

Figure 6.5 illustrates the most popular 200 words in the abstracts after training the bigram and the trigram terms. Overall, "Model", "data", "result", "area", "analysis", "system", "based", "project", "information", "study", "land_cover", "algorithm", "management" and "application knowledge" are some examples of words that are more frequently mentioned in the abstracts of the Masters' theses from NOVA IMS. 

### Adcionar Grafico

#### TOPIC MODELLING RESULTS 
####### LDA results 
Figure 6.7 allows uncovering the thematic structure of the Master’s theses dataset and shows the average prevalence of the topics for four different courses/specialisations in a given year. Overall, in each course/specialisation, there is a good match with the respective most dominant topic. This indicates that LDA has correctly discovered the latent topics in an unsupervised way. As an example, 
“GIS /Spatial/Smart_cities/Maps/Technology” 	and 
“Land_cover/Maps/Urbanism/Population/Environmental” are the dominant topics in Geographic Information System and Science but not in the other courses/specialisations. Another good example is the “Machine_learning_algorithms”, a dominant topic in “Data Science and Advanced Analytics”. It also has a good prevalence in “Knowledge Management and business intelligence” and “Risk Analysis and Management”, but it has less prevalence in “Geographic Information System and Science”. Additionally, it is possible to see the evolution of the topics in each course/specialisation. One good example is “Knowledge management and business intelligence”, which had very few topics initially. However, in recent years a considerable increase in topics in its theses can be identified. Figure 4 in the appendix provides information about other courses/specialisations. In each course/specialisation, there is good matching with the respective most dominant topic.

### Adcionar Grafico

##### BERTopic results
Figure 6.9 shows the average prevalence of the topics for four different courses/specialisations in a given year. Overall, it is possible to see that the courses/specialisations and their dominant topics match. Additionally, the top 25 words are semantically linked with the names of the courses/specialisations where they are dominant. This indicates that BERTopic has correctly and semantically discovered the latent topics in an unsupervised way. Some good examples to illustrate this are: 
•	Geographic Information System and Science now has one dominant topic (“Land_cover/GIS/Geospatial/Maps/Urbanism/Cities”) throughout the period. It is different from the LDA results, which had two;  
•	All topics discovered using BERTopic have a significant average weight in at least one of the courses/specialisations, different from LDA, where the topic “Self organising maps” does not have a significant average weight in any of the courses/specialisations; 
•	Another good example is the topic6 “GA/GP/GSGP/Machine_learning_algorithms”, which is one of the dominant topics in “Data Science and Advanced Analytics”. Its top 25 words are highly and semantically linked with the course/specialisation. 
Figure 5 in the Appendix provides information about other courses/specialisations. In each course/specialisation, there is good matching with the respective most dominant topic.

### Adcionar Grafico


#### CLUSTERING RESULTS
A hybrid clustering approach was used to find the clusters of the theses. In the first stage, SOM was applied. In total, 300 random maps were trained: 150 maps using topic vectors/features from LDA and 150 maps using topic vectors/features from BERTopic. In general, the maps using the topic vectors/features from BERTopic have lower values of QE than those from LDA (Figure 8, Appendix). The component planes of the topic vectors/features from BERTopic also show a better distribution of the theses than those from LDA. In most of the features from BERTopic, the theses are concentrated on one specific region of the map (Figure 9, Appendix). In contrast, in features from LDA, the theses tend to be dispersed all over the map (Figure 10, Appendix). Table 6.3 presents three (3) best parameter values that maximise the performance of mapping the theses using features from LDA and BERTopic. The solution with the lowest QE was selected for features from LDA and BERTopic.


The best match units (BMUs) found in the first stage, were used in the second stage. Ward was applied on the BMUs. After analysing the dendrogram (Figure 11, Appendix), the solution of 6 and 5 clusters using the topic vectors/features from LDA and BERTopic were selected, respectively. Figure 6.10 shows how the clusters are organised using features from each topic modelling algorithm. The final cluster solution using features from LDA shows that most of the theses are well clustered. However, some theses from clusters 2 and 4 are considered outliers, while features from BERTopic provide a better cluster solution. Most of the theses are placed in their natural group. Additionally, the arrangement of clusters enables the detection of the relatedness between them. Clusters located in the same region/nearby are more related. That is to say, the clusters have similar theses or theses with some similar topics. 

Clusters that are located far away are unrelated. That is to say, the clusters do not have similar theses or have theses with different topics.  Clusters 3 and 0 (Figure 6.10: SOM Heatmaps from LDA) are an example of related clusters, and clusters 1 and 3 (Figure 6.10: SOM Heatmaps from LDA) are unrelated clusters. To sum it up, the cluster located in the middle/centre of the others has overall relatedness. That is to say, the clusters have many similar theses to many theses from other clusters or theses with a good diversity of topics. At the same time, clusters located on the edge do not have overall relatedness or are more specific. That is to say, the clusters have many different theses to many theses from other clusters or theses with specific topics. Clusters 0 and 4 (Figure 6.10: SOM Heatmaps from BERTopic) are good examples of clusters with and without overall relatedness, respectively.


#### Network of the theses

##### The theses network results (LDA topic vector)
Figure 6.18 shows the interlinkages of the master theses from NOVA IMS modelled by using the LDA topic vectors. The arrangement of the network has a good similarity with cluster results. Several closer nodes/theses are part of the same cluster. The network and SOM heatmap (Figure 6.10: Heatmap from LDA) arrangements also have similarities. Clusters that share the same region on the SOM heatmap have their nodes/theses located in the same region/nearby in the network. At the same time, clusters located far away in the SOM heatmap have their nodes/theses located far away in the network. Additionally, several nodes/theses in the middle of the network also belong to the clusters located in the middle of the other clusters in the SOM Heatmaps. Finally, isolated nodes at the extremities of the network belong to the clusters located at the edge of the SOM Heatmaps. For instance: 
•	Cluster 0 (red nodes) and cluster 3 (yellow nodes) are located in the same region/nearby on the SOM Heatmaps from LDA (Figures 6.10 left image), and most of their nodes/theses are located in the same region/nearby in the network;  
•	Cluster 1 (blue nodes) and cluster 3 (yellow nodes) are the opposite of the above example;
•	Cluster 2 (Dark moderate magenta nodes) and Cluster 3 (yellow nodes) have a higher average for closeness centrality (Figures 6.15). Some nodes/theses from these clusters are located in the middle of the network. The SOM Heatmap from LDA (Figures 6.10 left image) illustrates that these clusters are also in the middle of other clusters. 
•	Theses from “Clinical Research Management” belong to cluster 0 (red nodes). They have topics not commonly found in other theses and are located in the extremities of the network. Moreover, analysing the SOM Heatmaps (Figures 6.10 left image) is possible to see that this cluster is also located at the edge of the map.
Besides these similarities in the results, a comparison between SOM and network visualisation shows that the network can reveal additional similarities between the theses even if they are from different clusters.

### Adcionar Grafico


##### The theses network results (BERTopic topic vector)
Figure 6.19 shows the interlinkages of the master theses from NOVA IMS modelled by using the BERTopic topic vectors. Overall, the network is dense, and some nodes are overlapping. Besides that, several closer nodes/theses are part of the same cluster. Furthermore, the network and SOM heatmap from BERTopic (Figures 6.10 right image) arrangement also have similarities. As an example, several nodes/theses from clusters 0 (Slightly desaturated cyan) and 1 (Soft red) are located in the middle of the network and the middle of the other clusters in the SOM Heatmap from BERTopic (Figures 6.10 right image). 

Cluster 0 (Slightly desaturated cyan) and cluster 3 (Dark moderate magenta) are located in the same region/nearby on the SOM Heatmap from BERTopic (Figures 6.10 right image). Therefore, most of their nodes/theses are located in the same region/nearby in the network. Cluster 1 (Soft red) and cluster 3 (Dark moderate magenta) are located far away in the SOM Heatmap from BERTopic (Figures 6.10 right image). Therefore, most of their nodes/theses are located far away in the network. 
Additionally, cluster 4 (Very light Yellow), characterised by the topic “Health Management Education” has several nodes/theses isolated nodes at the extremities of the network. This cluster is also located at the edge of the SOM Heatmap from BERTopic (Figures 6.10 right image).

### Adcionar Grafico


