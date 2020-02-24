# Blender Jams

<h2> Introduction </h2>

Blender Jams utilizes the Spotify API and Spotipy to pull song and artists data from Spotify. The purpose of Blender Jams is to allow users to automatically create customized playlists that are based on two artists, which are referred to as base artists. Once the base artists are specified, users can choose to search for songs only produced by the base artists or can choose to also look at songs from related artists. Blender Jams can use a combination of standardization techniques and basic distance metrics to calculate similarity between songs.

Similarity between songs is based on the Audio Features provided by Spotify. The audio features that were used to calculated similarity in this tool include the following: 

- acousticness
- danceability
- energy
- instrumentalness
- liveness
- loudness
- speachiness
- valence
- tempo

<h2> Methods </h1> 

The first step in the process is to specify the two artists to base the playlist around. Given that most people don't want a playlist that only contains two artists, the ability to pull songs from realted artists was added. Once artist and song data is pulled that information is used to pull audio information for each of the tracks. 

To increase the exploratory capabilites of Blender Jams, the ability to explore different standardization techniques and distance metrics was built into the tool. The available standardiztion techniques and distance metrics are given below. 

- Standardiztion Techniques:
     - None
     - Center: Mean center the data
     - Standardize: Mean center the data and then scale by the standard deviation
- Distance Metrics:
     - Cosine: Cosine similarity between track pairs
     - Euclidean: Euclidean distance between track pairs
     - Both: An experimental metric calculated as Cosine*(1/Euclidean)
     



<h2> References </h1>

1. Spotipy: https://spotipy.readthedocs.io/en/latest/# 
     - Used to interact with the Spotify API
2. https://scikit-learn.org/stable/
     - Used for PCA, Cosine Similarity, and Euclidean distance metrics
3. https://developer.spotify.com/documentation/web-api/
     - Spotify API used to pull song data and create customized playlists


