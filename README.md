# Project2
## Meredith Gray & Morgan Blanchard 

# Overview 
Project 2 involves ETL: extracting, transforming, and loading data. For this project, we wanted to analyze the most popular songs to see if there are recognizable trends among the top 50 songs in the United States. In order to look at this information we had to combine two datasets: one of Spoitfy top songs and one of musical data such as tempo, dancability, duration, energy. We can use this information to answer questions such as: do the most popular songs have a certain tempo range, is the dancability high or low for the top 50 songs, or are popular songs more likely to have a shorter duration? 

Our first dataset is Spotify top songs from 2017-2021 and can be found here: https://www.kaggle.com/dhruvildave/spotify-charts

Our second dataset contains the musical data as well as links to the songs from soundcloud and can be found here: https://www.kaggle.com/josshhh/spotify-songs-with-soundcloud-links

These datafiles are too large to be uploaded onto Github. Therefore, if you need to run the code it will be necessary to download the files from the links above. The first data file will be stored in the Data folder and named 'charts.csv'. The second data file will also be stored in the Data folder and will be named 'Soundcloud_data.csv'. The second data file does not download as a csv so it will need to be converted before the code will run. 

# Extract and Transform
We downloaded these two datasets and loaded them into a jupyter notebook using pandas. The first dataset ended up being nearly 20 million rows so we had to clean it up quite a bit. To clean the data, we removed 2017 and 2018 as we wanted the top 50 songs for the last two years, removed all top charts that were not in the US, pulled only the top songs from the first day of each month, and removed all duplicated songs. We pulled in the second dataset, removed any rows with missing information, and changed the column name of the song titles in order to merge the dataframes on that item. 

Once the dataframes are merged, we removed all repeated songs and had one dataset full of the top 50 songs alongside several musical data points. 

# Load 
To load the data onto MongoDB, we created a connection, then inserted our csv data into a dictionary that can be stored as a database. 