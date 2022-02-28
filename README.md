# Oh My Posh & Windows Terminal/Powershell

This is a configuration repository for everything in place to create a stylish terminal in Windows 10/11.

[Based on this video](https://www.youtube.com/watch?v=5-aK2_WwrmM&t=1037s)


## Step 0 : Install Windows Terminal

## Step 1 : install Nerf font : Hack
[Link](https://github.com/ryanoasis/nerd-fonts/releases/tag/v2.1.0)

## Step 2 : Change Windows Terminal Appearance
Haave the base theme on One Hald Dark, using Acrylic in tab bar and in console

## Step 3 : Install powershell (from MS Store)

Install Powershell from the MS Store and change it in Windows Terminal to the new Powershell

## Step 4 : Darken the terminal from the JSON settings file

Copy the One Half Dark theme and change it's name and also the background color to #001B26

## Step 5 : Install Scoop & stuff

iwr -useb get.scoop.sh | iex

scoop install curl sudo jq

## Step 6 : Install git and neo vim

winget install Git.Git

scoop install neovim gcc

## Step 7 : Configure Aliases inside vim for powershell & activate profile

mkdir .config/powershell

nvim .config/powershell/user_profile.ps1
Write
> # Alias
> 
> Set-Alias vim nvim
> 
> Set-Alias ll ls
> 
> Set-Alias g git
> 
> Set-Alias grep findstr
> 
> Set-Alias tig 'C:\Program Files\Git\usr\bin\tig.exe'
> 
> Set-Alias less 'C:\Program Files\Git\usr\bin\less.exe'


nvim $PROFILE.CurrentUserCurrentHost
> . $env:USERPROFILE\\.config\powershell\user_profile.ps1

## Step 8 : Check aliases in new terminal and install oh my posh! & add prompt to install

Install-Module posh-git -Scope CurrentUser -Force
Install-Module oh-my-posh -Scope CurrentUser -Force

nvim .config/powershell/user_profile.ps1

> #Prompt
> Import-Module posh-git
> Import-Module oh-my-posh
> Set-PoshPrompt Paradox

