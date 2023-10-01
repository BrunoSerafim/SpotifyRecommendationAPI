# Spotify Recommendation Python Class

This Python class, `SpotifyRecommendation`, allows you to interact with the Spotify API to retrieve information about artists, songs, audio features, and recommendations. It simplifies the process of authenticating with Spotify, making API requests, and extracting relevant data for music recommendations.

## Key Features

- **Authentication**: Automatically obtains an access token for the Spotify API using the client credentials flow.
- **Get Artist Genres**: Retrieve the genres associated with a specific Spotify artist by providing the artist's ID.
- **Get Track Audio Features**: Fetch audio features for a particular track, including attributes like danceability, energy, and tempo.
- **Get Available Genres**: Retrieve a list of available music genres for recommendations.
- **Get Song Recommendations**: Get recommended songs based on your specified parameters, such as seed tracks, artists, or genres.

## Usage Example

```python
# Initialize the SpotifyRecommendation class with your Spotify API credentials
spotify = SpotifyRecommendation(client_id, client_secret)

# Get an access token
spotify.get_headers()

# Get genres for a specific artist
artist_id = "some_artist_id"
genres = spotify.get_genre_artist(artist_id)
print("Genres:", genres)

# Get audio features for a track
track_id = "some_track_id"
audio_features = spotify.get_audio_features_track(track_id)
print("Audio Features:", audio_features)

# Get available music genres for recommendations
available_genres = spotify.get_available_genres()
print("Available Genres:", available_genres)

# Get song recommendations based on specified parameters
params = {
    "seed_artists": ["some_artist_id"],
    "limit": 5
}
spotify.get_songs(params)
