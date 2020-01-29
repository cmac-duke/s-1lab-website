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

<!-- DOCUMENTATION FOR S-1 LAB -->

# For S-1

Note that the directions below can be found on Hugo's website (gohugo.io) as well as in the documentation for the Academic theme (https://sourcethemes.com/academic/docs/), especially under "Managing Content."

## Setting up the environment

### Make a GitHub account

Go to https://www.github.com and make an account. Then have someone invite you to the cmac-duke group (github.com/cmac-duke). The site's repository is on there (github.com/cmac-duke/s-1lab-website).

### Install git

- In Windows, I recommend either using the GitHub graphical application or downloading MSYS2 (a terminal program that works like Unix systems and uses Arch Linux's package manager: pacman) from https://www.msys2.org/ and entering ```pacman -S git```.

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
<blockquote>
    If you are required to enter your GitHub credentials every time you push changes to the repo on GitHub, then follow these directions to cache your password: https://help.github.com/en/github/using-git/caching-your-github-password-in-git
</blockquote>

### Install Hugo
If on Linux, then follow your distribution's package manager or use snap:
```
snap install hugo --channel=extended
```
It's important to include the "extended" argument in our case, otherwise it won't build the site. This is a requirement of the "Academic" theme we're using.

On Mac, install [homebrew](brew.sh).

Then use homebrew to install hugo:
```
brew install hugo
```

In the future, you may update your homebrew packages by entering: `brew update`

### Cloning the repo

Navigate to where you want to keep a clone of the repository on your system. If you are using the command line for the first time, there are plenty of tutorials for navigation. You'll likely only need to use three commands: pwd (present working directory), cd (change directory), and ls (list). And remember, you can press TAB to autocomplete your destination.

Once you're where you want to be, clone our website's repository ("repo" for short) with the following command, which you can copy and paste (usually with Cmd/Ctrl + Shift + V):

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

### Making sure it works

You need to get into the command line in order to use Hugo. While this is not strictly necessary for changing the website, I recommend it so you can make sure your changes actually work.

While in the s-1lab-website directory (you can be anywhere in it, not only the top directory), type `hugo` and press enter. This builds the site, which means hugo goes through all the files and turns them into browser-legible html, which get deposited in a newly made public/ directory. 

<blockquote>
    Sidenote: The public/ directory is not part of the repository. One of the hidden files (these start with a period) in a git repository is ".gitignore". It lists all the files and subdirectories that are excluded by git's tracking.
</blockquote>

When working on the site, you may need to delete this directory between builds to avoid conflicting files. This can be done by entering `rm -rf public/` into the command line.

To view the site, run `hugo serve` and enter "localhost:1313" in your internet browser.  

## Contributing to the site

### Work on a separate branch

First and foremost, I recommend working within a different branch from the "master" branch. This is part of git, which is a version control system. Think of it like a copy of the repository that enables you to tool around without worrying about messing up the project. If you end up liking what you change, then you can merge it with the master branch. I will walk you through how to do this. Know that there are plenty of tutorials for these functions, including the official one: (https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging).

Before I explain how to do that, ensure that your local repository is up to date with the original one upstream on github.com:
```
git fetch origin
git merge
```
"Origin" refers to where the GitHub repository is hosted. It should already be set up when you cloned the repo. You can confirm this by running `git remote -v`.

Now you're ready to make your own contributions on a fresh branch.

To list currently available branches, enter the following into your terminal (as with the above steps, this will only work while working within the directory of a git repository):
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
git add .
```
and then
```
git commit -m "Type in your commit message here."
```
Or do it all at once:
```
git commit -a -m "Enter your commit message here."
```
The argument "-a" condenses the separate command "git add .", which adds all untracked files listed with the "git status" commmand. Note that if you are doing a lot of modifications, it is best practice to add specific files or groups of files and commit them in bunches. To do this, simply replace the period in the "git add" command ("." is short for all files within the directory) with the pathways to the files. For example, let's say I wanted to commit changes I had made to a bunch of author files. To do so, I would run `git add content/authors/` and then run a commit as above. Afterwards, running ```git status``` should confirm that those files are no longer either untracked or staged for commit.

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

Why bother with this last step? Because branches do not automatically keep up to date with each other. You could come back to work on the site and, as before, begin by merging your local "master" branch with the original one on github. At that point, your old "dev" branch will be out of date. Alternatively, everytime to return to the dev branch, you could merge it with master.

Lastly, run the following command to add your new changes to the origin repo on GitHub:
```
git push
```

## Creating and editing content

Now we're getting to what makes Hugo and other static site generators useful. You can do the bulk of your site building in markdown (.md files) so long as your site's html templates have been set up. And, since the templates are separate from the individual markdown pages, you can change the layout of the website by modifying a template and/or its CSS.

Since you'll mostly be working in markdown, here's the link to the official documentation on formatting: https://www.markdownguide.org/basic-syntax

### Adding and editing a member

When using Hugo, you can make new files with different templates from the command line. Let's start with the case of an author for the site. For us, these populate the "Members" and "Alumni" pages on the main site page.

First, enter the following in the terminal:
```
hugo new --kind authors authors/firstname-lastname
```
<blockquote>
  If you're making an alumni member, then you will want to substitute alumni/ for authors/. Of course, when someone leaves the lab, you can drag the particular member's folder to the alumni directory and change their user groups accordingly.
</blockquote>

This creates a new folder within the content/authors/ subdirectory. And within that new folder it has created two files: an "_index.md" file and an "avatar.jpg" file. First, let's modify the markdown file to display the new author on the website.

<blockquote>
  You can refer to mine (authors/David-Rambo/) as an example. You'll see that I've replaced my organization "- name:", which for most of you is "Duke University", with my own text. The Academic theme is set to provide some simple icons for various websites like GitHub and Twitter.
</blockquote>

Open the newly created "_index.md" file and make sure that the display name on line 2 is correct. After that, scroll down and adjust any of the interests, courses, or other info that come with the template. For anything you do not want to include, simply add a hash (#) at the beginning of those lines. Most importantly, at the bottom you will find a list of user groups. All of the options are listed in content/home/people.md. Apply the correct user group (e.g. "- Graduate Students"). After saving, you should see the new name and its avatar.jpg displayed on the home page.

<blockquote>
  These options are all in what is called frontmatter, which is separated out by three hyphens "---" at its beginning and end. The Academic theme uses YAML ("Yet Another Markdown Language") for its frontmatter. Another popular option is TOML ("Tom's Obvious Markdown Language"), which you'll recognize by its usage of three addition signs "+++" in lieu of hyphens as well as a lot of square brackets for its keys/variables/parameters.
</blockquote>

To change the avatar, replace the image with another .png or .jgp file that has been named "avatar". (Note that JPEGs also use .jpg for their file suffix.)

To add a bio, type below the frontmatter's closing "---". Be sure to use markdown to format it. This means single asterisks for italics, double for bold, triple for italicized bold. Headings are formatted with hashes (i.e. pound signs). If you want to use an asterisk without it being transformed by Hugo into text formatting, using an "escaping character" (https://www.markdownguide.org/basic-syntax#escaping-characters).

### Adding other content

Other files such as projects and events follow a similar format. Each has its own template, which is called by the specific "hugo new" command entered into the terminal command line.

To create a new project:
```
hugo new --kind projects projects/give-it-a-name
```

To create a new event:
```
hugo new --kind event event/hear-ye-hear-ye
```

As with members in the authors/ subdirectory, these pages are presented on the site dependent upon the tags given to them. You should be able to follow the examples of those already provided. Remember that the options are in the corresponding widget page within content/home/.