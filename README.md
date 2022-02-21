# Music Generation

## Purpose:
Music Generation allows you to find ringtone on Spotify,
then give that song to `tensorflow-magenta` for it to continue your ringtone.

## Run 
```
python3 main.py name\ song\ from\ spotify and\ another\ one
```

Result `.mid` file is in `outputMusicGeneration/` directory.

`tensorflow-magenta` works best with classical music,because of conversion to `.mid`,
I highly do not recommend using any music with a human speech in it.

## How it works 
1. Searches for your query song on Spotify (because Spotify has better search than YouTube does)
2. Searches that song on YouTube 
3. Downloads `.mp3` from YouTube (download speeds are very slow because I guess google somehow blocks network traffic from `youtube_dl`)
4. Converts `.mp3` to `.wav` --- higher quality == better conversion to `.mid`
5. Converts `.wav` to `.mid` (`tensorflow-magenta` works only with `.mid`)
6. Loads pretrained model for `magenta`
7. Continues all the `.mid` files and saves them to `outputMusicGeneration/`
8. Deletes temporary files

## Requirements
1. Make [WaoN](https://github.com/kichiki/WaoN) as `waon` in the same folder as `main.py` file
2. `spotipy`
3. `youtube-search`
4. `youtube-dl`
5. `magenta`

## TODO 
1. Use Jupyter notebook instead of `.py` file
2. Improve [RNN](https://en.wikipedia.org/wiki/Recurrent_neural_network) model
3. Change `youtube-dl` to something better to download videos faster than `60kb/s`
