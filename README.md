# express-starter
Express - boilerplate NodeJS project with setup guide

I'm writing this guide for macOS/Linux.  Open an issue if you'd like to see a Windows guide.

# macOS Setup

## Install Homebrew
Open the Terminal.app in macOS.  Copy and paste the following command and press `ENTER`.
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
This will install Homebrew on your local machine.  Homebrew is a trusted package manager for macOS.  You can do things like `brew install google-chrome` and it will install the app for all users on you machine.

Check for errors here and if all looks good try to run the command `brew -v` and that should return something like `Homebrew 4.0.21`.

## Install NodeJS
At the time of writing this NodeJS 18 is LTS (Long-Term Support).  It's the recommended version for the next couple of years.

To install NodeJS using Homebrew copy and paste this command into the terminal like the previous step.
```bash
brew install node@18
```

Next run the following command in the Terminal.app
```bash
echo 'export PATH="/opt/homebrew/opt/node@18/bin:$PATH"' >> ~/.zshrc
```
This tells your machine where to find the NodeJS executable (program/command).  *You'll need to close your Terminal.app now.*  Make sure to quit it from the menu bar at the bottom of the screen (Two-finger click and Quit).  Then once the dot has disappeared you can reopen it and go to the verify step.

_Alternative_ - Install from a pkg
Follow this link to go to a graphical install of NodeJS - (NodeJS Official Website)[https://nodejs.org/en]
It should be noted that we'll use Homebrew in other steps so if there's an issue with installing Homebrew it's better to resolve early. 

### Verify NodeJS install
Run the following command in the Terminal.app
``` bash
node -v
```
You should see something like `v18.16.0`


## Install an IDE (_preferrably VS-Code_)
An IDE is an Interactive Development Environment.  This is where you write, run, and test code.  If you already have one setup than skip to the next step.  

To install VS-Code from the Terminal.app run the following command (copy/paste)
```bash
brew install --cask visual-studio-code
```

## Install Git if it's not already installed
To check if Git is already installed run the following command in the Terminal.app
```bash
git -v
```

If you get an error than please follow the next step.  If you see a version number Git is installed.

## Install Git
```bash
brew install git
```

## Clone this repo!
Cloning a repository is just copying the source code to you local machine from the Github website.  To do this go to a directory that you would like to store the folder in the terminal.

If you don't care where it lives run the following in the terminal (otherwise follow the Terminal 101 steps).  It will copy the repo into a folder with the same name locally.
```bash
git clone git....
```

### Terminal 101
When you open up a terminal session (also called the command line or CLI) you are placed in the `HOME` directory.  In macOS this is a shortcut for `/Users/<YOUR_USERNAME>` to verify this run `echo $HOME` in you terminal.  `echo` is a command for shell script.  Shell script (`sh`) is the programming language used in terminals.  Not really important here.

To navigate folders (directories) we use the `cd` command - aka _change directory_.  Most terminals have `TAB` complete which means you can type the first part of a folder and tab and it should complete the rest.

Let's go to your Desktop.  From the terminal type `cd ~/Desk` and press tab.  It should complete to the Desktop directory of your machine and then press enter.

What's happening here?  `cd` is changing the directory to `~/Desktop`.  The `~` symbol is a shortcut to your `HOME` directory and you started to tell the terminal the folder you want starts with `Desk`, when you hit tab it completed based on the first match.  

macOS has a really cool feature where you can drag the folder you want into the terminal to get its path.  For example drag the desktop folder into the terminal and it should say `/Users/<YOUR_USERNAME>/Desktop`.  You can use this to navigate to the directory of your choosing by finding or creating one in the Finder then type `cd ` and drag and drop the directory you'd like to change to.

To go _up_ the file tree to the parent directory type `cd ..`.  To go all the way to the root you can type `cd /` but storing code there is not recommended.

Let's make a `Code` directory withing the `HOME` path.  First let's run `cd ~` to make sure we're in the `HOME` directory.  Then run `mkdir Code`.  This will create a new directory to store projects in.  

List contents `ls` - this will print out a list of a directories contents _except for hidden files_. To see all files you can run `ls -a`.  You should see a `Code` directory amongst a list of others if you ran the previous step.  To change to this directory run `cd Code`. _Now go back to the previous step and clone your repo here_.

Present working directory `pwd` - this give you a file path to your current directory

## Install the NodeJS dependencies.
If you've just cloned the directory in the previous step you should be able to type the following into the terminal:
```bash
cd express-starter
```

Run the `ls` command and you should see a package.json file and others.  

NodeJS's package manager uses a command called `npm` Node Package Manager.  To install all the dependencies for a project run:
```bash
npm install
```
from the project directory.  This can take a couple of minutes.  

## Run the APP!!!!
If the install step completed without error you can now run:
```bash
npm start
```

This tells NPM to look at the `package.json` file for a run command called start.  It's a shortcut, but in most NodeJS apps this is how application are triggered.  You can also run `node index.js` from the the terminal, but it's not best practices.  

You should see something like listening on localhost:8080

Viola!  You just ran a web-app locally.





