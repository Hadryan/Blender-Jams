# Blender-Jams

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

References: 
1. Spotipy: https://spotipy.readthedocs.io/en/latest/# 
     - Used to interact with the Spotify API
2. https://scikit-learn.org/stable/
     - Used for PCA, Cosine Similarity, and Euclidean distance metrics
3. https://developer.spotify.com/documentation/web-api/
     - Spotify API used to pull song data and create customized playlists


