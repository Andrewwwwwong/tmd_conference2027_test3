This is the source code for the 2DTMD2023 website.

The website is built using Jekyll.

There are github actions set up for automatic deployment.

# Local Installation

To build the website out of the templates, we use a thing called Jekyll.

Jekyll is written in Ruby, hence we need to install that first:

Mac (apparently):
brew install ruby

Windows is a pain:
https://www.ruby-lang.org/en/documentation/installation/#rubyinstaller


## Now we need to install jekyll:

https://jekyllrb.com/
gem install bundler jekyll

## Running Jekyll

you should be able to navigate into the tmd_conference folder and run

bundle install

bundle exec jekyll serve

and then head to

http://localhost:4000/

and the website should be there.

The actual website source is generated automatically and put into the _site folder.

# The Website Content

In almost all cases, the content within the website is loaded from data files found in `tmd_conference/_data`.

These are then used by the templates in `tmd_conference` to build the pages. 

# The Program

To enable rapid updating of the online program, the program is defined in a excel file on the google cloud.

This file should have the format of the file `program.xlsx`.

A github action is used to fetch this file prior to building and deploying the website.

A simple python script (`create_program_csvs.py`) converts this `.xslx` file into `.csv` files and places them into the `tmd_conference/_data` directory before the website is built.

If testing locally, one needs to use Python, and install the requirements from `requirements.txt`, then run `python create_program_csvs.py`.

# Dev and Prod.

The github repo is set up such that there is a dev (development) and prod (production) branches.

Updates to branches with these names are automatically deployed.

The development branch builds the website, but adds `/dcuenvoieuriewud2dhfhf/` infront of all URL addresses to obscure them. This allows changes to be tested on the remote server.

# Github Secrets.

* `SFTP_ADDRESS` - The IP address of the remote server the website is hosted on. The deploy actions upload the contents of `_site` to this address via SFTP.
* `SFTP_USERNAME` - The username for the SFTP server.
* `PASSWORD` - The password for the SFTP server.
* `PROGRAM_FILE_ID` - The [file id](https://robindirksen.com/blog/where-do-i-get-google-drive-folder-id) of the `program.xslx` file on google drive.


