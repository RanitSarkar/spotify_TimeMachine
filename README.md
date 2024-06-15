# Billboard Hot 100 Scraper and Spotify Playlist Creator

## Step 1 - Scraping the Billboard Hot 100

1. **Create a new project in PyCharm and create the `main.py` file.**

2. **Create an input prompt:**
    ```python
    date = input("Enter the date you would like to travel to (YYYY-MM-DD): ")
    ```

3. **Scrape the top 100 song titles on the specified date:**
    - Use BeautifulSoup to scrape the song titles into a Python List.
    - Example URL for historical chart: `https://www.billboard.com/charts/hot-100/2000-08-12`

## Step 2 - Authentication with Spotify

1. **Create a Spotify account:**
    - Sign up for a free account [here](http://spotify.com/signup/).

2. **Create a Spotify App:**
    - Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/) and create a new Spotify App.
    - Copy the Client ID and Client Secret into your Python project.

3. **Authenticate with Spotify:**
    - Use the Spotipy library for easier authentication.
    - Follow the [Spotipy documentation](https://spotipy.readthedocs.io/en/2.13.0/#spotipy.oauth2.SpotifyOAuth) to authenticate your project.
    - Use `http://example.com` as your Redirect URI and set it in the Spotify Dashboard.
    - Ensure you have the `playlist-modify-private` scope.

4. **Get the current user ID:**
    - Use the [Spotipy `current_user` method](https://spotipy.readthedocs.io/en/2.13.0/#spotipy.client.Spotify.current_user) to get your Spotify username.
    - The user ID is found in the `id` key of the returned dictionary.

## Step 3 - Search Spotify for the Songs

1. **Create a list of Spotify song URIs:**
    - Use the list of song names from Step 1.
    - Format the query as `track:{name} year:{YYYY}` to search for the track.
    - Handle exceptions for songs not available on Spotify.

## Step 4 - Creating and Adding to Spotify Playlist

1. **Create a new private playlist:**
    - Name the playlist `YYYY-MM-DD Billboard 100`, where the date is the input date from Step 1.
    - Use the user ID from Step 2.

2. **Add songs to the new playlist:**
    - Use the playlist ID returned when the playlist is created.
    - Add each song from the list of Spotify song URIs.

---

**Note:** This README is a guide for developers to create a Python project that scrapes the Billboard Hot 100 chart and creates a Spotify playlist with the top 100 songs for a given date. Make sure to follow the detailed documentation of Spotipy and BeautifulSoup for specific implementation details.
