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

## Setting up the environment

### Install git

- In Windows, I recommend using either the GitHub graphical application or downloading MSYS2 (a terminal program that works like nix systems) and entering ```pacman -S git```.

- Mac OS already has git installed.

- For Linux, use your distribution's package manager. For example, for debian/Ubuntu distros: 
```
sudo apt install git
```
Or, for arch and arch-based distros like Manjaro:
```
sudo pacman -S git
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

Next, you need to activate the submodules that go with the theme we're using: Academic. To do this, run the following two commands:

```
git submodule update --init --recursive

git submodule update --remote --merge
```

