# BASH HELPERS

## Setup

If you don't have OhMyZsh installed, install that first as it makes the terminal so much nicer to use.

1. If it doesn't exist, create a folder in your home (`~`) directory `/bin`
2. Clone this repo to to `~/bin`: 
```
cd ~/bin
git clone git@bitbucket.org:nusxtra/bash-helpers.git ./
```
3. Export to your PATH environment variable:
```
cd ~
nano .zshrc
```
Add the next 2 lines to the bottom of the file, save and exit
```
# Bash helpers
export PATH=~/bin:~/bin/private:"$PATH"
```
4. Restart your shell.
```
exec zsh -l
```

That is it, you are good to go... all scripts in the `~/bin` folder are accessible via the terminal from any location. Best of all tab autocompletion works! Type in `gita` and press `tab` and it will autocomplete to `gitAcp` (git add-commit-push).


## Permission denied

If you see an error like this:
```
zsh: permission denied: gitStatus
```

Then the bash script is not executable. Ensure you have the correct execute permissions on your bash scripts in your `~/bin` folder.
```
cd ~/bin
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
Bash scripting is often quite bespoke to a developers environment/workplace. Recommend to create a fork and personalise this for your best working env. If you have some generic scripts that could apply to everyone send in a PR... ensure the naming convention is followed and ensure the script is executable when pushed to git! 🚀