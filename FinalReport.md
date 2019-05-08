# Final report
This is the final report for the IBM Applied Data Science Coursera specialization.

## Introduction/Business Problem
Belgian capital Brussels is the administrative seat of European Union. People who want to work for one of the European institutions often have to move there. It is something that quite some people I know - and are also from the European country of Slovenia - decided to do. 

Moving to a capital of another country is a big step, so it would help to know you are moving to a similar neighbourhood that you lived in your home country. How similar or dissimilar are parts of Brussels compared to Ljubljana?

For the project, I will take Bežigrad, one of Ljubljana’s - capital of Slovenia - representative, mostly residential districts and compare it to the 19 municipalities of the Brussels-Capital Region. The goal is to find municipalities that are the most similar in terms of venues to the Ljubljana’s representative district.

## Data

I will make the comparison based on the type of venues that are the most common in the district and municipalities. I will then perform a grouping using machine learning to determine which of the municipalities are most similar to Bežigrad district.

I will be using data from Foursquare. The service enables us to search for specific venues at a certain location. Venues are places like coffee shops, restaurants, shops, parks etc. I will focus on types of venues, not names so that they are comparable across different locations.

For example, if the district is residential, you expect there to be a lot of small grocery stores, some coffee places etc. If the district is industrial, touristy or business oriented, the types of venues that are most frequent will be different. I will not do the analysis by myself but compare the data with machine learning techniques to determine the most similar municipalities.

The data used will be the list of 19 municipalities of the Brussels-Capital Region from Wikipedia. I will add the name of Bežigrad district to the scrapped list. From there, I will use Google Geocoding API data to get the coordinates of the district and municipalities. That will give me a dataframe I can use to get the data from Foursquare. I will then use k-means (machine learning technique for grouping) with different amount of centroids to determine how close are specific Brussels districts to Ljubljana’s Bežigrad district.

## Methodology

Before deciding on the project, I have checked the data about Brussels and Ljubljana to see that comparison would make sense. I learned that Brussels has a population of about 1.2 million people and is split into 19 municipalities, ranging in population from about 22.000 to 177.000. Ljubljana has a population of about 280.000 and is divided into 17 distristics. They range in population from about 4.700 to about 35.000 people. 

Based on this analysis I decided to compare Bežigrad district, which has a population of about 34.500 with the municipalities. Given the population data, the district might as well be one of the municipalities of Brussels.

The second concern I addressed was if Foursquare has enough data for Ljubljana to make a comparison with a bigger and more global city. Running a test query and making some manual searches on the service itself convinced me that there is enough data to proceed.

To make the comparison and determine similarities between Brussels municipalities and Ljubljana’s Bežigrad district I used a K-means clustering method. This is an unsupervised machine learning method. 
The goal of K-means clustering is to find groups in the data. K stands for the number of groups. Data points are clustered based on similarity of the features. So the more similar the data features, the more likely they will be grouped. 

A trivial example: if my data consists of an apple, a peach and a car and I would have a K-means algorithm separate them in two groups (K=2),  an apple and a peach should be put in one group, and a car in the second. I have ran this algorithm to group the Brussels municipalities and Ljubljana’s district to determine how alike they are given the Foursquare venues data.

## Results
When I tried with splitting data into three groups, I was surprised to find that Bežigrad district was in the group with most of the Brussel’s municipalities. The algorithm put them all in cluster 0, while only Woluwe-Saint-Lambert was put in cluster 1 and only Molenbeek-Saint-Jean, two of the Brussels municipalities, were put in cluster 2. 

That result tells me that it is more similar to most of the municipalities than two of the city’s own. Based on the data obtained from Foursquare, most of the municipalities should be a decent approximation to Ljubljana-Bežigrad.

## Discussion
As I went further, increasing the number of groups to four or five, Ljubljana-Bežigrad still remained in the largest group. It stayed like that even when increasing to seven. That’s why I believe that the result with three groups is enough.

## Conclusion 
Regarding the question of which municipality of Brussels is similar* to Ljubljana-Bežigrad, any municipality but Woluwe-Saint-Lambert and Molenbeek-Saint-Jean fit the bill. 

*Similarity is determined based on the Foursquare data and comparison of “venue type” frequency utilising K-means analysis using three and five clusters.
