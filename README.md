# youtube-download


Download simples de vídeos e playlists do YouTube usando a biblioteca [PyTube](https://github.com/nficano/pytube)

### Instalação
```bash
pipenv install
```

#### Download de um vídeo
```python
def download_video(video_url):
	yt = YouTube(video_url)
	video = yt.streams.get_highest_resolution()
	video.download()
```

#### Download de uma playlist
```python
def download_playlist(playlist_url):
	playlist = Playlist(playlist_url)
	for url in playlist:
		yt = YouTube(url)
		video = yt.streams.get_highest_resolution()
		video.download(output_path='playlist')
```

#### Download do áudio
```python
def download_audio(video_url):
	yt = YouTube(video_url)
	audio = yt.streams.filter(only_audio=True)[0]
	audio.download()
```