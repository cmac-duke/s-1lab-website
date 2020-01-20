# [Academic Kickstart](https://sourcethemes.com/academic/)

**Academic** makes it easy to create a beautiful website for free using Markdown, Jupyter, or RStudio. Customize anything on your site with widgets, themes, and language packs. [Check out the latest demo](https://academic-demo.netlify.com/) of what you'll get in less than 10 minutes, or [view the showcase](https://sourcethemes.com/academic/#expo).

**Academic Kickstart** provides a minimal template to kickstart your new website.

- [**Get Started**](#install)
- [View the documentation](https://sourcethemes.com/academic/docs/)
- [Ask a question](http://discuss.gohugo.io/)
- [Request a feature or report a bug](https://github.com/gcushen/hugo-academic/issues)
- Updating? View the [Update Guide](https://sourcethemes.com/academic/docs/update/) and [Release Notes](https://sourcethemes.com/academic/updates/)
- Support development of Academic:
  - [Donate a coffee](https://paypal.me/cushen)
  - [Become a backer on Patreon](https://www.patreon.com/cushen)
  - [Decorate your laptop or journal with an Academic sticker](https://www.redbubble.com/people/neutreno/works/34387919-academic)
  - [Wear the T-shirt](https://academic.threadless.com/)

[![Screenshot](https://raw.githubusercontent.com/gcushen/hugo-academic/master/academic.png)](https://github.com/gcushen/hugo-academic/)

## Install

You can choose from one of the following four methods to install:

* [**one-click install using your web browser (recommended)**](https://sourcethemes.com/academic/docs/install/#install-with-web-browser)
* [install on your computer using **Git** with the Command Prompt/Terminal app](https://sourcethemes.com/academic/docs/install/#install-with-git)
* [install on your computer by downloading the **ZIP files**](https://sourcethemes.com/academic/docs/install/#install-with-zip)
* [install on your computer with **RStudio**](https://sourcethemes.com/academic/docs/install/#install-with-rstudio)

Then [personalize your new site](https://sourcethemes.com/academic/docs/get-started/).

## Ecosystem

* **[Academic Admin](https://github.com/sourcethemes/academic-admin):** An admin tool to import publications from BibTeX or import assets for an offline site
* **[Academic Scripts](https://github.com/sourcethemes/academic-scripts):** Scripts to help migrate content to new versions of Academic

## License

Copyright 2017-present [George Cushen](https://georgecushen.com).

Released under the [MIT](https://github.com/sourcethemes/academic-kickstart/blob/master/LICENSE.md) license.

[![Analytics](https://ga-beacon.appspot.com/UA-78646709-2/academic-kickstart/readme?pixel)](https://github.com/igrigorik/ga-beacon)

# For S-1

Note that the directions below can be found on Hugo's website (gohugo.io) as well as in the documentation for the Academic theme (https://sourcethemes.com/academic/docs/), especially under "Managing Content."

## Setting up the environment

### Install git

- In Windows, I recommend using either the GitHub graphical application or downloading MSYS2 (a terminal program that works like nix systems) and entering ```pacman -S git```.

- Mac OS already has git installed.

- For Linux, use your distribution's package manager. For example, for debian/Ubuntu distros: 
```
sudo apt install git
```

Then, configure some basic settings. For your github user account info, enter the following and replace your credentials into the square brackets (excluding the brackets from the command, but keeping the quotation marks):
```
git config --global user.name "[USERNAME]"

git config --global user.email "[EMAIL-ADDRESS]"
```

### Install Hugo
If on Linux, then follow your distribution's package manager or use snap:
```
snap install hugo --channel=extended
```
It's important to include the "extended" argument in our case, otherwise it won't build the site.

On Mac, install [homebrew](brew.sh).

Then use homebrew to install hugo:
```
brew install hugo
```


### Cloning the repo
Navigate to where you want to keep a clone of the repository on your system. Then, clone it with the following command:

```
git clone https://github.com/cmac-duke/s-1lab-website.git
```

Next, you need to activate the submodules that go with the theme we're using: Academic. To do this, run the following command:

```
git submodule update --init --recursive
```
In the future, you may update by typing in the following while in the website's directory:
```
git submodule update --remote --merge
```
Why is this necessary? Because the theme/ folder for the website is actually a container for the Academic repository. Cloning our S-1 Website does not initially include those files.

## Contributing to the site

### Work on a separate branch

First and foremost, I recommend working within a different branch from master. This is part of git's version control system. Think of it like a copied version that enables you to tool around without worrying about messing up the project. If you end up liking what you change, then you can merge it with the master branch. There are plenty of tutorials for these functions, including the official one: (https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging).

Before I explain how to do that, ensure that your local repository is up to date with the original one upstream on github.com:
```
git fetch origin
git merge
```
Now you're ready to make your own contributions on a fresh branch.

To list currently available branches enter the following into your terminal (as with the above steps, this will only work while working within the directory of a git repository):
```
git branch
```

To make a new branch called "dev" and automatically switch to it, enter the following in the terminal:
```
git checkout -b dev
```

As you work, you can type in "git status" to see a list of all the files you've modified, including new ones and deleted ones.

Once you're happy with the work you've done, add the files and commit them:
```
git commit -a -m "Enter your commit message here."
```
The argument "-a" condenses the separate command "git add .", which adds all untracked files listed with the "git status" commmand. Note that if you are doing a lot of modifications, it is best practice to add specific files or groups of files and commit them in bunches. To do this, simply replace the period in the "git add" command ("." is short for all files within the directory) with the pathways to the files.

The argument "-m" allows you to add a commit message in the same command. Otherwise you will be prompted to do so in a terminal text editor.

Okay, so you've modified your repository, but it's still confined to the "dev" branch. To transfer those changes to the master branch, here's what you'll need to do:

Return to the "master" banch.
```
git checkout master
```

Merge with the "dev" branch's changes.
```
git merge dev
```

Finally, delete the "dev" branch so that you can remake it in the future.
```
git branch -d dev
```

Why bother with this last step? Because branches do not automatically keep up to date with each other. You could come back to work on the site and, as before, begin by merging your local "master" branch with the original one on github. At that point, your old "dev" branch will be out of date. This presents problems when merging the two.

Lastly, run the following command to add your new changes to github:
```
git push
```

### Adding an author/member
When using Hugo, you can make new files with different templates from the command line. Let's use the case of an author for the site. For us, these populate the "Members" and "Alumni" pages.

First, enter the following in the terminal:
```
hugo new --kind authors authors/firstname-lastname
```
This creates a new folder within the authors/ subdirectory. And within that new folder it has created two files: an "_index.md" file and an "avatar.jpg" file. First, let's modify the markdown file to display the new author on the website.

Open the newly created "_index.md" file and make sure that the display name on line 2 is correct. After that, scroll down and adjust any of the interests, courses, or other info that come with the template. For anything you do not want to include, simply add a hash (#) at the beginning of those lines. Most importantly, at the bottom you will find a list of user groups. All of the options are listed in content/home/people.md. Apply the correct user group (e.g. "- Graduate Students"). After saving, you should see the new name and its avatar.jpg displayed on the home page.