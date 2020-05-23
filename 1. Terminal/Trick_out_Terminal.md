# Trick out Terminal

If you're going to use Terminal all day long, why not make it prettier?

*Brought to you by @theevo*

*2020-05-21*

## Assumptions

1. macOS
2. zsh (is default in macOS 10.15). To be sure, run `echo "$SHELL"`. Response should be `/bin/zsh`
3. You know how to navigate in Terminal. [Tutorial](https://learn.co/lessons/bash-navigation-osx).
4. You understand how [hidden files](https://www.macrumors.com/how-to/show-hidden-files-on-a-mac/) in macOS are named.
5. You know what ~ means in command line.


---

## Oh My Zsh


### 1. Install Oh My Zsh

Open up Terminal.app and copy + paste in the following command:

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

source: [ohmyz.sh](https://ohmyz.sh/#install)


### 2. Install Dracula Theme for your Terminal

[https://draculatheme.com/terminal](https://draculatheme.com/terminal)

1. Follow "Install Manually"
2. Then "Activating theme"


### 3. Make a code folder outside of iCloud Drive

Why? My group's project used CocoaPods. What we experienced was duplication of Pods because of iCloud Drive. It added several hours of delays that could have been avoided if all of us had stayed the heck away from iCloud Drive.

Get commitment from all of your teammates that you won't store your group in an iCloud Drive folder or subfolder.

Here's a safe place to house your code.

The following commands will create a folder called "code" in your Home folder. 

```
cd ~
mkdir code
```

When it's time to clone your project, cd to your code folder then clone.

```
cd ~/code
git clone <your group repo link>
```

### 4. Make your code folder the default location




### Where to "Oh My" from here?

[OMZ Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

[OMZ wiki](https://github.com/ohmyzsh/ohmyzsh/wiki)

Google powerlevel9k and be in awe

---

## gitignore


### 1. Copy a trusted person's .gitignore

[Theo's gitignore](https://gist.github.com/theevo/09bcdd508f9d65edfda637487143a877)

[If you don't trust me, at least trust GitHub.](https://github.com/github/gitignore/blob/master/Swift.gitignore)

### 2. Paste into Textedit

### 3. Name it `.gitignore` and save to ~/code

gitignore is prefixed by a dot (aka period)

### 4. Install it for your configuration of git

```
git config --global core.excludesFile ~/code/.gitignore
```

### 5. When you're working with a group, one of you should add + commit a copy of your gitignore file.

The gitignore file copy should be at the root of your project folder.

```
cp ~/code/.gitignore ~/code/group_project
```


---

## git config

### 1. Tell git your name and email

macOS will set your email address in git to something like `johndoe@MacBook-Air.local`. Let's fix that.

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

Maybe you'll get hired because someone saw your commit message to an open source project. 😉

### 2. Tell `vi` to take a hike

When you ever have to merge a conflict on your local machine, you'll be forced to create a mandatory commit message in the default text editor of zsh, which `vi`.

I personally hate `vi`. The idea that commands begin with a colon sickens me. :q to quit? 🤮

Let's fix that.

1. Open TextEdit
2. Open ~/env.sh
3. You have options here. Pick one.

Text Editor Options

1. `pico`. Command line text editor. Way more intuitive.
2. TextEdit. The GUI text editor of macOS.

If you chose `pico`, change this line:

```
export EDITOR=pico
```

If you chose TextEdit, change this line:

```
export EDITOR="/System/Applications/TextEdit.app/Contents/MacOS/TextEdit"
```

4. Save

You're done with git config!


