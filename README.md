# Slack-Downloader
Easy way to back up all files from slack

# Why you need it?

Most people don't want to pay for high Slack monthly subscription fees where all files are stored forever. Most plans have around 3 months of expiry.
So being in a start-up where some files are important and we don't want to lost the data this script can help you save stuff locally and avoid asking people to resend files you need 3 weeks later

# How to run?

Pre-requisite: Python is installed on your local environment

1. Clone this repository into your local computer.
1. `cd` into the folder
1. Run `pip install requests` to download dependency
1. Do `chmod +x slack-downloader.py` to ensure its executable
1. Open the `slack-downloader.py` script with a text editor and configure it using a [legacy token](https://api.slack.com/custom-integrations/legacy-tokens)
1. Optionally, you can add the program to your `crontab` to automatically check for new shared items on Slack:

   ```
   crontab -e
   ```
1. Now you have to append the following line (press `i` button to insert data):

   ```
   0 * * * * python /directory_path/slack-downloader.py
   ```

   where `/directory_path/` identifies the path of the directory containing the script, while `0 *` specifies the program has to be called every hour.
   You can use this to set your own [cron job schedule](https://crontab.guru)
   
1. Run using the command `python slack-downloader.py`
1. All data will be stored in this format
   ```
    <channel_name>/<date>-<filename>_by_<user/uploader>.<ext>
   ```
   History of already downloaded files is mantained, in order to avoid duplicate downloads.

