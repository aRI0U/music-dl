# MusicDL

This command line tool enables to download the audio of a YouTube video given the URL of the file.

## Usage

```
music-dl -- <URL>
```
download the audio from video whose URL is `<URL>`

### Options

`-c`: Keep only pitched audio file with AAC encoding, remove original audio file and `wav` auxiliary files.

`-o <fname>`: change the name of the output audio file. Default is `output`.

`-p <N>`: increases the pitch of the audio file by a number of `N` semitones (can be negative number).

#### Example
In order to download the audio from a YouTube video whose URL is `<URL>`, raise its pitch by one tone (2 semitones) and write it in a file called `audio1.m4a` in the (existing) directory `myMusic`, run
```
music-dl -c -o myMusic/audio1 -p +2 -- <URL>
```

## Setup
As the program is a simple Bash script, there is no need to install anything. However, it uses the following utilities:
* [youtube-dl](https://ytdl-org.github.io/youtube-dl/index.html)
* [ffmpeg](https://www.ffmpeg.org/)
* [Rubber Band](https://breakfastquay.com/rubberband/)
Please refer to the webpage of the corresponding packages to install them.

After having installed those dependencies, execute the following commands:
```
sudo wget -nc https://raw.githubusercontent.com/aRI0U/music-dl/master/music-dl -O /usr/local/bin/music-dl
sudo chmod a+rx /usr/local/bin/music-dl
```
Then add the following line at the end of your `.bashrc` file to be able to run the script with a single command:
```
alias music-dl='/usr/local/bin/music-dl'
```
and run `source .bashrc`.
