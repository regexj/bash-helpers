# BASH HELPERS

## Foreword

This is a compilation of bash scripts I've written over the years to speed up my own development. They will work on UNIX based systems (Linux/Mac) but probably not Windows without some additional work. If they can help you out then please clone and use freely! :-)

## Setup

If you don't have OhMyZsh installed, install that first as it makes the terminal so much nicer to use.

1. If it doesn't exist, create a folder in your home (`~`) directory `/bash-helpers`
2. Clone this repo to to `~/bash-helpers`: 
```
cd ~/bash-helpers
git clone git@github.com:regexj/bash-helpers.git ./
```
3. Export to your PATH environment variable:
```
cd ~
nano .zshrc
```
Add the next 2 lines to the bottom of the file, save and exit
```
# Bash helpers
export PATH=~/bash-helpers:~/bash-helpers/private:"$PATH"
```
4. Restart your shell.
```
exec zsh -l
```

That is it, you are good to go... all scripts in the `~/bash-helpers` folder are accessible via the terminal from any location. Best of all tab autocompletion works! Type in `gita` and press `tab` and it will autocomplete to `gitAcp` (git add-commit-push).


## Permission denied

If you see an error like this:
```
zsh: permission denied: gitStatus
```

Then the bash script is not executable. Ensure you have the correct execute permissions on your bash scripts in your `~/bash-helpers` folder.
```
cd ~/bash-helpers
chmod -R +x *
```


## Naming convention

```
<program><shorthand command><recursive flag>
```

- program = the program the script will mainly use, eg git
- command = a shorthand command acronym eg Wip.. "work in progress"
- recursive = if a script is recursive, e.g. traversing down every sub folder, end it with `-r`


## Example
Add, commit and push code to your branch as one liner:
```
gitAcp "Feat: platform integration"
```
This will run the following commands:
```
git add .
git commit -m 'Feat: platform integration'
git push
```

## Developing
Bash scripting can often quite bespoke to a developers environment/workplace. Recommend to create a fork and personalise this for your best working env. If you have some generic scripts that could apply to everywhere send in a PR... ensure the naming convention is followed and ensure the script is executable when pushed to git! 🚀