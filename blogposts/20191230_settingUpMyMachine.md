# New Year (dev env) Resolution

When I started working on my current job I had changed my main working environment from Windows to Ubuntu 16 because I need to use  docker an at the time I was too lazy to setup docker toolbox in Windows and  use it in WSL. And today as I upgrade my OS to Windows 10 Pro and I get access to Hyper-V, thus docker for Windows. So to start the year I am migrating my environment from Ubuntu into WSL for Windows again. And since currently my environment is not documented and relatively messy, by the spirit of new year, I started again from zero in setting up my WSL environment based on my learning in Ubuntu and also  what I wanted to do in my environment for the next year. I guess I will see it as my new year dev environment resolution.

## Scope

I will not talk about how to install WSL and which environment to pick since I picked Ubuntu 18 since I wanted the latest LTS Ubuntu. And there are a lot of information in the web about how to install and setup them.

For several details I will linked it to my own reference site, and maybe I will also add several details on what doesn't work and what works for me.

## My Aims

For this setup what I wanted to do is as follow:

1. I needed to be able to modify my theme and plugins easily
2. I wanted to familiarized myself with vim and tmux for the next year
3. I wanted to improve my abilities in navigating and utilizing command line to inspect files/folders
4. At work I mainly working with python and I need a way to manage my python environment
5. And for my work I still need to be able to access vs code as currently it enables me to be more productive
6. I need to manage my keys better as my work requires me to manage several keys to access cloud services
7. At home I tend to work using javascript
8. Most of the documents I made in last year were made using Latex, Markdown and Google Office Suite
9. In this year I am planning on learning several languages to enrich my view (Haskell, Go, and Clojure)
10. I wanted to build my workflow around the terminal so that most routine that I do need to be accessible in terminal

Hmmmm quite a lot of things that I wanted to achieve here, I don't know if I can fulfill all of them, but using those aims at least I have several setups that I know I wanted to have in my WSL environment. A lot of things that I did were inspired by thoughtbot and Nick Janetakis and I highly recommmends people to check out both blogs.

## 0. What Terminal to Use?

Searching around, I used to be a hyper person and then cmder, but experiencing high latency in writing in terminal, I chose to try out mintty based terminal wsltty as it offers better performance and I actually didn't really use hyper's features.

## 1. Installing zsh and zplug

### Installing zsh

``` bash
sudo apt install zsh

# after finished run this to set zsh as default shell
chsh -s $(which zsh)
```

then restart your terminal to see the changes

### Installing Zplug

Link to zplug github for install guide
Using several plugins from oh my zsh inspired by [Oktavera's Setup](https://github.com/okitavera/dotfiles/blob/master/.zshrc)
Some plugins used and theme. And additional script from [TerribleCode's Blog](https://www.terriblecode.com/blog/zplug-from-a-former-oh-my-zsh-user/) to auto update on startup

### Several obstacles

I face the obstacle of compinit considered the .zplug folder as unsafe. It appears that I need to change the owner and permission for its folder [as stated in SO](https://github.com/zsh-users/zsh-completions/issues/433)

Permission denied when using ".." or "~" not yet found any leads on this

## Setting up Tmux and VIM

Nick janetakis tmux setup and simple vimrc

### Install Tmux

``` bash
sudo add-apt-repository ppa:pi-rho/dev
sudo apt-get update
sudo apt-get install tmux-next

# Rename tmux-next to tmux:
sudo mv /usr/bin/tmux-next /usr/bin/tmux
```

Install TPM
- tmux-resurrect
- tmux-continuum

### Tmux workflow

## Basic CLI needs

- make
- curl
-

## Additional Utilities Command Line

Here are several utilities that I have installed

- fasd for better navigation
- au/ag and ripgrep
- bat
- exa
- jq
- fzf

## Setup Python environment

## Docker Environment

## Extra: Additional Looks and Feels

### Theme used

Powerlevel9K with several added settings:

- maximum dir length
- default username
- conda environment

Font used: Firacode using ligatures

but for now I started considering [pure](https://github.com/sindresorhus/pure) as alternative.
