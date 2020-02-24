# Blender Jams

<h2> Introduction </h2>

The scope of work of this work was to create a series of functions capable of building playlists around a set of two artists. The motivation for this work was prompted by the fact that Spotify provides users a variety of pre-built playlists, artist-centric radio stations, and best of an artist playlists. However, custom playlist building is usually done manually by the user, which may limit the user's exposure to new artists and songs that they may like. Therefore I set out to create a tool called Blender Jams.  

The hope is the Blender Jams will provide users with a simple one-click solution for creating custom-built playlists based around two artists at the click of a button. The playlists may contain songs from related artists that will help increase user's exposure to artists that are similar to their favorite artists they haven't listened to before. The ultimate goal is to give users more control over the playlists provided by Spotify and increase their exposure to new artists.

The purpose of Blender Jams is to allow users to automatically create customized playlists that are based on two artists, which are referred to as base artists. Once the base artists are specified, users can choose to search for songs only produced by the base artists or can choose to also look at songs from related artists. Blender Jams can use a combination of standardization techniques and basic distance metrics to calculate similarity between songs.

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
     
Once the similarity between track pairs is calculated the track pairs with similarities in the 75'th precentile are isolated for further analysis. The user can choose to randomly select songs from the 75'th precentile of similarity or take to top 10 similar pairs. Once the similar tracks are pulled the user specifies the name of the playlist to save their songs into. Blender Jams will then create a playlist with the similar 

<h2> Essential Fucntions </h2>

<pre><code>
def get_similar_tracks(artist_pair,              # A list containing the name of two artists to base the playlist on
                       get_related = True,       # Whether or not to pull tracks from related artists 
                       scaleing = None,          # Whether to scale the data prior to calculating similarity
                       sim_metric = 'cosine',    # Distance metric used to calculate similarity
                       random_top_tracks = False # Whether to take the most similar tracks or to randomly choose from 75'th percentile
                       )

def create_playlist( track_ids,                             # Output from get_similar_tracks(...)
                     playlist_name = 'Blender Playlist',    # Name of the playlist
                     replace = True )                       # If a playlist with the same name exists, whether to replace the tracks in it
</code></pre>

<h2> References </h1>

1. Spotipy: https://spotipy.readthedocs.io/en/latest/# 
     - Used to interact with the Spotify API
2. https://scikit-learn.org/stable/
     - Used for PCA, Cosine Similarity, and Euclidean distance metrics
3. https://developer.spotify.com/documentation/web-api/
     - Spotify API used to pull song data and create customized playlists


