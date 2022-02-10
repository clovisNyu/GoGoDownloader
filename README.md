
<div align="center">
  <img
    style="width: 300px; height: 300px"
    src="https://github.com/karl0ss/GoGoDownloader/raw/master/img/gogo_logo.png"
    title="GoGoDownloader"
    alt="GoGoDownloader"
  />
  <h3>GoGo Downloader</h3>
  <h4>Forked from <a href="https://github.com/karl0ss/GoGoDownloader">GoGoDownloader</a></h4>
  <p>
    A Python script that allows you to download all of an anime's episodes at once. Includes a CLI to run scripts programatically, allowing for automated scheduling of downloads as well as automatically downloaded new episodes of ongoing anime.
  </p>
 
</div>

## About GoGo Downloader

GoGo Downloader is based on the now broken **BitAnime**. I have had to rework quite a bit of the code to get it working again, and have ideas for some other improvements, I don't want to mess with the original codebase too much, hence **GoGo Downloader**.

**GoGo Downloader** gets its content from [gogoanime](https://gogoanime.film/). If you get a **404** error, please look up the correct anime name on [gogoanime](https://gogoanime.film/). The application will let you download all the episodes, or you can choose how many episodes you want to download.

GoGo Anime has changed the way they show download links, and this no longer works via BS4, as the recaptcha blocks the links, but if you are logged in, there are other routes to get to download links, I have taken one of these routes to restore the application.

## Features

- Download all qualities options from GoGoAnime
- Update the current GoGoAnime domain via config file (as they keep changing it)
- Specify the number of concurrent downloads via config file (Max is 6)
- Set file overwrite via config file (0 = Skip / 1 = Overwrite)
- Run the script from the CLI using GoGoAdhoc.py

## Installation
- Clone the repository
- Edit config.json accordingly
- Add your GoGoAnime Username and Password to config.json (Can't be a Google account)
- Run the app with `python GoGoDownloader.py` or run the CLI tool with `python GoGoAdhoc <url> --archive <path_to_archive_file> --quality <360|480|720|1080>`

## Screenshot

<div align="center">
  <img style="height:386px; width:688px;" src="https://github.com/karl0ss/GoGoDownloader/raw/master/img/screenshot.png"
  title="BitAnime in action" alt="BitAnime Screenshot">
</div>

## Dependencies

**GoGo Downloader** is highly reliant on the python modules `requests`, `colorama`, `parfive`, and `BeautifulSoup`.

## Usage

The anime name is separated by "-". You can either type it manually, or go to [gogoanime.film](https://gogoanime.film/) and search for the anime you want to download and copy the name from the URL.

To use the CLI, go to the folder container the source code from a terminal and use the command:
`python GoGoAdhoc <url> --archive <path_to_archive_file> --quality <360|480|720|1080>`

### Examples

##### One word title

- https://gogoanime.film/category/bakemonogatari >> bakemonogatari
- https://gogoanime.film/category/steinsgate >> steinsgate

##### Multiple word title

- https://gogoanime.film/category/shadows-house >> shadows-house
- https://gogoanime.film/category/kono-subarashii-sekai-ni-shukufuku-wo- >> kono-subarashii-sekai-ni-shukufuku-wo-

##### CLI
- `python GoGoAdhoc "https://gogoanime.film/category/leadale-no-daichi-nite" --archive test --quality 1080`

The above code will find all episodes for the anime "Leadale no Daichi Nite" and check against the local file "test" (if it exists) to see which episodes have already been downloaded. It will then download all episodes that have not been downloaded at 1080p and then add the successfully downloaded episodes to the archive file "test"
