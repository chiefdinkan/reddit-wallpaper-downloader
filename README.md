# Reddit Wallpaper Downloader

This script downloads wallpapers from various subreddits on Reddit.com, and saves them in a directory of your choice. The user can choose which subreddit to download the wallpapers from or enter a custom subreddit of choice. ```which technically makes this a reddit-random-image-downloader (.❛ᴗ❛.)  ``` ,And how many wallpapers or posts they want to download.

Install these dependencies if you don't already have them installed.
## Dependencies

- curl
- jq

## Usage

1. Clone this repository or download the `reddit-wallpaper-downloader.sh` file.
2. Make the file executable with the command `chmod +x reddit-wallpaper-downloader.sh`.
3. Run the script with the command `./reddit-wallpaper-downloader.sh`.
4. Enter the number of wallpapers you want to download when prompted.
5. The downloaded wallpapers will be saved in the `$HOME/Pictures/Wallpapers` directory (or the directory specified by the `$WALLPAPER_PATH` environment variable).

## How it works

1. The script sends a request to the Reddit API to get the JSON data for the latest posts in the selected subreddit , limited to 100 posts at a time.
2. The script then randomly picks a post from the returned JSON data that has an image link hosted on i.redd.it, reddit.com, or i.imgur.com.
3. If the post is a gallery, it randomly selects an image from the gallery.
4. The script fetches the image link and saves it as a .jpg file with a filename that includes the date and time the image was downloaded, as well as the title of the post.

## Caveats

This script is designed to download wallpapers from Reddit, but there are a few caveats you should be aware of.

#### Only Gets the 100 Most Recent Wallpapers

The script only retrieves the 100 most recent wallpapers from the API to choose from. This means that if you run the script multiple times without deleting the images it previously downloaded, it may end up re-downloading the same images.

#### Possible Parse Error

In some cases, the script may encounter a parse error due to issues with the cached JSON file in `/tmp/`. To solve this issue, simply delete the JSON file and then re-run the script.

## License

This script is licensed under the GPL-3.0 License. See the LICENSE file for more information.
