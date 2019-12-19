# pdp_site
This is the new pdp site


# Team
Derek - setup complete
Jay
Marty
Ernie
Jason


# SETUP

## Homebrew / Chocolately
First download a package manager on your command-line (CLI) that will provide us with `git` and `hugo`.

For macOS use [Homebrew](https://brew.sh/). Paste this command in your CLI and run it.

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`


For Windows use [Chocolately](https://chocolatey.org/). Paste this command in your CLI/Powershell and run it.

`Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-ObjectSystem.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`

## Git and Hugo
Next we need to install the packages we need. We need Git to be able to commit our changes to the codebase and Hugo to have the framework to build our site.

Run these commands based on which package manager you have.

### Git
`brew install git`
`choco install git.install`

### Hugo
`brew install hugo`
`choco install hugo`


## VS Code

Next you need a code editor to be able to actually write code. I recommend downloading [VSCode](https://code.visualstudio.com/). This is the most popular code editor on the market right now for software development.

## Cloning
Now we need to clone this git repo (code base) into our computer so we have a copy of it. Make a folder somewhere in your desktop where we can store our code, navigate into it in your CLI (using `cd`/`chrdir`) and run this:
`git clone https://github.com/ernie-h/pdp_site.git`
This should clone the pdp_site code on github into this folder.

After cloning open up pdp_site in VSCode and you should see all the files we can edit.
