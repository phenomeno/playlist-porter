# Playlist Deli

## Usage

###  Obtain credentials
```
bundle install
ruby server.rb
```
Sign in to Spotify.

### Create sample playlists based on what artists you like
```.ruby
require_relative 'app'
user_hash = JSON.parse(File.read('credentials.json'))
spotify_user = RSpotify::User.new(user_hash)

playlist_sampler = PlaylistDeli::Tasks::Sampler.new(spotify_user)

# ['recent', 'short_term', 'medium_term', 'long_term']
playlist_sampler.create_new_mix!('recent')
```
