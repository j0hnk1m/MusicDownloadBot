# ShazamShortcut

A Python script and webpage that uses Google's OCR API to automatically download your Shazam songs in one click to your Downloads folder, which can be added automatically to your local computer for easier syncing with your phone. Designed to make life easy.

Many people who do not have Spotify premium resort to not listening at music or downloading music files from the internet, moving it to the iTunes folder, and syncing iTunes to their phones. Many people also use Shazam, whether integrated with Snapchat or the Shazam app itself, whenever they hear a song they like. This workflow shortcut, dubbed "ShazamShortcut," aims to combine the two common actions together and streamline them together into a simple automated process.

Our basic automated workflow available as a button on our webpage is: 1. Get user's Shazam songs through screenshots 2. Use Google OCR (Image to text conversion) API to extract song name and artist from screenshots 3. Search youtube for a lyric video of that song and download it to the server computer 4. Add thumbnails for extra flair and flex 5. Combine all songs and compress into a folder to download it to the client's computer

A concise description of files: - main.py = does all the action, from opening the shazam webpage and taking screenshorts - ocr.py = converts shazam song screenshot image to text - music.py = downloads the music and thumbnails automatically given a song and artist name from Youtube - app.py = server file using Flask - ui.html = web page UI - coin.wav = sound effect every time a song is done downloading - Pipfile + Pipfile.lock = Pipenv files that allow the program to work across other computers (similar to virtualenv, conda env, and pyenv)

Extra notes not described above: - searches for specifically lyric videos because lyric videos, in contrast to their official VEVO music videos, tend to not have scenery/fillers at the beginning and end that don't contain music. Now there's no need to wait 30 seconds for the music file to actually end! - could not web scrape Shazam because of the song names and artists being loaded into the webpage as javascript code/links, so web scraping would require selenium to acquire full DOM including javascript links. Selenium was also incompatible because the absence of cookies would result in the user having to verify their email every time they need to log into their Shazam account → OCR on screenshots was the only option left - screenshotting was done in a smart and efficient manner by controlling the mouse and keyboard with the pyautogui module - avoids downloading duplicate songs by looking for mp3 files that contain the song and artist name in the filename - designed for the user's utmost comfort/laziness. All the user needs to do is shazam songs on their phones, and the program will automatically download them to their respective computer
