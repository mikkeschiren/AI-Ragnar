# AI Ragnar - the slow but safe way to transcribe files

Transcribe your audio and video files locally.

This is a fork of <https://github.com/mickekring/ragnar>. Focus is to make it more secure, update to Python 3.13 etc. Parts will be contributed back from another repo.

![ragge_header](https://github.com/user-attachments/assets/fbb54afb-ec4a-462f-b24f-c3ee056e3ea8)

## What is this?

AI Ragnar is a simple app built with Python and [Streamlit](https://streamlit.io/) that transcribes your audio and video files locally on your computer, or your own server. Secure and without any need to call out to any services but your own computer.

Though it needs to be connected to the internet to download the modules.

It uses [Whisper](https://github.com/openai/whisper) and [KB Whisper (from Kungliga Biblioteket)](https://huggingface.co/collections/KBLab/kb-whisper-67af9eafb24da903b63cc4aa).

The transcriptions can then be saved as txt, docx, json and srt (subtitles).

## How the app works - flow

1. When you run the app, a web page is opened in your default web browser.
2. You upload an audio- or video file directly from the app.
3. When you've uploaded audio, the audio file will be converted into an mp3 file and compressed in size.
4. The mp3 file will be transcribed using Whisper or KB Whisper locally on your computer based on your settings (language and model).
5. The transcribed text is presented to you with the possibility to download.

## Recommended way of running Ragnar

Use docker:

```shell
docker-compose build
docker-compose up (-d)
```

Visit: <http://127.0.0.1:8501>

## Dev installation

This is an early beta, but it works. Expect updates as I develop this app. If you have any suggestions, feel free to ask.

* Tested on Mac OSX and Windows 10 with Python 3.12
* Download the files and 'pip install -r requirements.txt'
* Install FFMPEG on your system
* Run with 'streamlit run app.py' alternatively 'python -m streamlit run app.py'
* The first time you run it, it will take som time since the Whisper model is downloaded to your computer.
* If you're on Windows, I included a 'ragnar.bat' file which starts the application if you place all code in 'C:\ragnar'. You can edit this if you place Ragnar in a different folder.
