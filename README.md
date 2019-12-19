# pdp_site
# Team
 * Derek - Setup complete
 * Jay
 * Marty
 * Ernie - Setup complete
 * Jason


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
Now we need to clone this git repo (codebase) locally so we have a copy of it. Make a folder somewhere (i.e workspace) on your desktop where we can store our code, navigate into it in your CLI (using `cd`/`chrdir`) and run this:
`git clone https://github.com/ernie-h/pdp_site.git`
This should clone `pdp_site` from github into this folder.

After cloning open up `pdp_site` folder in VSCode and you should see all the files we can edit.

## Running hugo locally
Now that we have `pdp_site` on our computer we have to try running the site locally. Running the site locally means using hugo to start up a server instance through our CLI that temporarily hosts our site until the session closes. In VSCode you can click `Terminal -> New Terminal Window` and it will open up a CLI in the code editor. After that make sure you are in the root of `pdp_site` (i.e Desktop/workspace/pdp_site). Then run the following command:

`hugo -D server`

This should start up a web server on the address `http://localhost:1313/`. Using any browser navigate to that URL and our website should be live.

## Hot Reloading
Hugo supports hot reloading, which means that any change to HTML, CSS, JS, or Markdown files will be instantly reflected on the site after saving. For example, if you add an image to the home page and save the file, the browser automatically refreshes and reflects the change you made.

## Workflow
Once you've cloned the codebase, made some changes, and are ready to publish your changes, there is a workflow you must follow so that we don't step over each other.

Before we start make sure we have the latest version of `master` locally. Run the following:

`git checkout master` This makes sure we have checked out into our master branch
`git fetch` This will fetch the latest changes, if any, from github's master
`git pull` This will pull any new changes from `origin/master` and merge them into our local copy of `master`

1. **Feature Branch** -
Before working on any new changes you must create a feature branch off of `master` describing what you are working on.
`git checkout -b <FEATURE_BRANCH_NAME>`
Ex. `git checkout -b homepage`

2. **Stage Changes** -
After creating a new branch, you can start working on your feature. Once you are confident you have finished your feature, you can begin the process of pushing it up to github for others to see. Run a `git status` to see what files you have modified and double check those are what you want to commit. Run a `git diff` to have a more in-depth review of specific lines that you have modified. 
Afterwards, in order to stage your changes run `git add .`. The `.` opeartor indicates you are staging all files for commit. If you only want to add select files you can run `git add <FILE_NAME>` Ex. `git add homepage.html`

3. **Commit Changes** -
Next we have to commit the staged changes into a single commit. A commit is basically a reference of all the changes you have staged for publishing. Run `git commit -m "COMMIT_MESSAGE"`. The commit message should specify what changes are included in the commit. Ex. `git commit -m "Added hero image to homepage"` 

4. **Push Refs and Changes** -
Once you have commited your changes run `git log` to double check that your commit is at the `HEAD` of your work tree. Type `:q` to exit out. Now you are ready to push your changes to github. Run `git push`, note that this should throw a error message. You should receieve a separate push command in your console like the following, `git push --set-upstream <remote> <branch>`.
What this means is that your branch only exists locally and there is no reference to it on github. Again at this point github has no reference of any branches, commits, or changes you have made locally. `--set-upstream` specifies that we are setting a reference of our current branch on git hub. Ex. `git push --set-upstream origin homepage` Means that we are creating a reference of the branch `homepage` on github for us to push to. 
Once you run this you will receive a prompt to login with your github credentials. The reason for this is that github needs to be able to verify that you are allowed to push changes to this specific repo. If it didn't, any one would be ablt to push to our site. For now you can just enter your credentials and your changes will be pushed, however, this might start to get annoying as you begin pushing more changes. There is a way for you to add ssh keys to your CLI config files, which will validate with github that you are indeed allowed to post to this repo and will remove the hassle of writing your credentials each time. For more info see [this](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

5. **Make Pull Request** -
Once your changes are pushed, navigate to github on your browser and you should see a prompt on the repo to **compare and request** your branch. Click the green button, write a description, and create the pull request. Now all of your changes will be highlighted in this pull request for others to review.

6. **Wait for Peer Reviews** -
There is a section where you can request collaborators to review the work you've done. For our case this is important because others might be working in the same files as you and this gives us transparency on what everyone else is working on. Notify others to look at your PR and wait for an approval of it before merging.

7. **Merge Pull Request** -
Once you get the :+1: click the green button on the bottom that says **Merge**. Make sure to delete your branch after you have merged to master.

8. **Update Your Master** -
Lastly, navigate to your CLI session in VSCode and again run a `git fetch` and `git pull`. Remember to keep your local copy of master updated with the new changes you have just published. And thats it :fire:!
