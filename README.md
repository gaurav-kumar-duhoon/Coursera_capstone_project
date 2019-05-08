<h1>Final Report</h1>

<h3>Introduction/Business Problem</h3>
Belgian capital Brussels is the administrative seat of European Union. People who want to work for one of the European institutions often have to move there. It is something that quite some people I know - and are also from the European country of Slovenia - decided to do.

Moving to a capital of another country is a big step, so it would help to know you are moving to a similar neighbourhood that you lived in your home country. How similar or different are parts of Brussels compared to Ljubljana?

For the project, I will take Bežigrad, one of Ljubljana’s - capital of Slovenia - representative, mostly residential districts and compare it to the 19 municipalities of the Brussels-Capital Region. The goal is to find municipalities that are the most similar in terms of venues to the Ljubljana’s representative district.

<h3>Data</h3>
I will make the comparison based on the type of venues that are the most common in the district and municipalities. I will then perform a grouping using machine learning to determine which of the municipalities are most similar to Bežigrad district.

I will be using data from Foursquare. The service enables us to search for specific venues at a certain location. Venues are places like coffee shops, restaurants, shops, parks etc. I will focus on types of venues, not names so that they are comparable across different locations.

For example, if the district is residential, you expect there to be a lot of small grocery stores, some coffee places etc. If the district is industrial, touristy or business oriented, the types of venues that are most frequent will be different. I will not do the analysis by myself but compare the data with machine learning techniques to determine the most similar municipalities.

The data used will be the list of 19 municipalities of the Brussels-Capital Region from Wikipedia. I will add the name of Bežigrad district to the scrapped list. From there, I will use Google Geocoding API data to get the coordinates of the district and municipalities. That will give me a data frame I can use to get the data from Foursquare. I will then use k-means (machine learning technique for grouping) with different amount of centroids to determine how close are specific Brussels districts to Ljubljana’s Bežigrad district.
