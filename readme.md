## About
[vimify](https://github.com/MuAnsari96/vimify) is a plugin for [Vim](https://github.com/vim/vim) that provides simple Spotify integration. Since it uses the MPRIS2 dbus interface to control Spotify, it works out of the box with all Linux systems, provided that the Vim installation was compiled with python. Using this plugin, users can search for spotify tracks, browse through artists and albums, and completely control the playback of tracks through the desktop version of Spotify, all without leaving the comfort of Vim!

## Features and Usage
vimify is designed to interface with a running desktop instance of Spotify. Currently, the following features are supported:

* `:SpPlay` will play the current track
* `:SpPause` will pause the current track
* `:Spotify` or `:SpToggle` will toggle play/pause
* `:SpSearch <query>` will search spotify for 'query' and return the results in a new buffer. While working in the Vimify buffer, the name, artist and album of all pertinent tracks will be displayed. Vimify's behavior in this buffer is described as follows::
    * `<Enter>`: If the cursor is over the name of the track, Spotify will begin playback of that track
    * `<Enter>`: If the cursor is over the name of the artist, all of the artists tracks will be displayed, sorted chronologically and by album
    * `<Enter>`: If the cursor is over the name of the album, all of the tracks on the album will be displayed in the proper order 
    * `<Space>`: Is bound to `:SpToggle` when working in the Vimify buffer

## Installation 
The preferred way to install vimify is to use [pathogen](https://github.com/tpope/vim-pathogen). With pathogen installed, simply run
```bash
cd ~/.vim/bundle
git clone https://github.com/MuAnsari96/vimify
```
update March 2018: Vimify now requires authentication.

1. Create a new spotify application at https://beta.developer.spotify.com/dashboard/applications
2. Grab the Client Id and Client secret of your brand new spotify developer application
3. Go to https://www.base64encode.org/ and paste your client id and secret like client:secret. example: 

```
afff3bbbdffff7ebclientID452855f9:afff3bbbdffff7secretfdfd452855f9
```

4. Grab the encoded result to your clipboard and paste it in your vimrc like:

```
let g:spotify_token='YOURENCODEDRESULTHERE'
```

* It's bit of an extra step to encode it, but safes code in the plugin, plus you
won't be putting a hard-coded password in your env files (though a bas64 string is easy
to spot and more than easy to reverse!!!!).

And you'll be good to go! Once help tags are generated, you can just run `:help vimify` in vim to see the manual.

