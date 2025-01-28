# Git for Dummies, Mac edition

A guide on how to use git commands in Mac's terminal (command line), instructions mostly apply to PC as well. Commands in git and terminal (command line) will be explained and presented to provide insight into what can be done. The guide will use a factory metaphor to give Industrial Engineering and Management students the opportunity to understand git from a more familiar perspective.

[1. Factory Metaphor - industrial engineering student perspective]

[2. Terminal commands (a selection)]

[3. Git commands]

[4. Import a set-up project in Eclipse]

[5. FAQ]

[6. Miscellaneous - good to know + glossary]

[7. Remaining questions to investigate]

[8. Android programming]

[9. But what if you're running Windows?]

[10. Pro Tip]

[11. Additional Documentation]

[1. Factory Metaphor - industrial engineering student perspective]:https://github.com/Alexandermafi/git_for_dummies#1-fabriksmetafor--industrial-engineering-student-perspective
[2. Terminal commands (a selection)]:https://github.com/Alexandermafi/git_for_dummies#2-terminal-commands-a-selection
[3. Git commands]:https://github.com/Alexandermafi/git_for_dummies#3-git-commands
[4. Import a set-up project in Eclipse]:https://github.com/Alexandermafi/git_for_dummies#4-Import-a-set-up-project-in-Eclipse
[5. FAQ]:https://github.com/Alexandermafi/git_for_dummies#5-faq
[6. Miscellaneous - good to know + glossary]:https://github.com/Alexandermafi/git_for_dummies#6-Miscellaneous--good-to-know
[7. Remaining questions to investigate]:https://github.com/Alexandermafi/git_for_dummies#7-Remaining-questions-to-investigate
[8. Android programming]:https://github.com/Alexandermafi/git_for_dummies#8-android-programing
[9. But what if you're running Windows?]:https://github.com/Alexandermafi/git_for_dummies#9-But-what-if-you-re-running-Windows
[10. Pro Tip]:https://github.com/Alexandermafi/git_for_dummies#10-pro-tip
[11. Additional Documentation]:https://github.com/Alexandermafi/git_for_dummies#11-Additional-Documentation


# 1. Factory Metaphor - industrial engineering student perspective

- git status -> Lets you see what goods you have in stock

- git add -> Loads the goods onto the loading dock

- git commit -m "message" -> Loads the goods into the truck. The goods are marked with the note "message"

- git push -> Sends the truck to the recipient

- git pull -> Receives a truck full of goods that are put into storage

- git fetch -> Receives a truck full of goods but does NOT put them into storage

# 2. Terminal commands (a selection)

These are all the commands that work in the terminal.

| Command | Function |
| ------ | ------ |
| cd | Change directory – change folder |
| cd . | |
| cd .. | |
| cd ~ | changes to your home folder (user) |
| cd folder1/folder2/folder3 | Changes to folder 3, which is in folder2 etc |
| touch filename | Creates a new file named filename |
| ls | Shows visible files and folders in the current location |
| ls –a | Shows all (including hidden) files and folders in the current location: -a is called a flag for ls |
| rm filename | deletes the file filename. Doesn't work with folders |
| rm –r foldername | Recursively deletes all contents in a folder |
| rm –rf foldername | Recursively deletes the folder named foldername. rf stands for recursive force which means it doesn't ask for permission when it's unsure, which it can be if something unexpected happens. For example, if there are files in subfolders. This command is specific to Mac (actually unix), on PC it's: rm foldername. VERY POWERFUL, so be careful. E.g., rm-rf * will delete EVERYTHING... |
| nano README.md | Opens the file README.md in the terminal with the nano editor. You can then change the content directly in the terminal. Only applies to UNIX systems. |
| vim README.md | Opens the file README.md in vim. Vim is cool (street cred in the IT world – kind of like driving an Aston Martin among I:are). |
| man command | Brings up a detailed description of the command. EX: man cd |
| command --help | Brings up a shorter help for a command |
| ctrl + c | Interrupts the current command |
| grep –r searchterm | Searches recursively in ALL FILES for the search term. Very powerful! Can be used with wildcard (*) |
| cat ~/.ssh/id_rsa.pub | Opens your ssh key so you can add it to github |
| EXTREMELY MUCH MORE | Google |

# 3. Git commands

All commands that have to do with git start with git, followed by the command name. This tells the terminal to use git and run the subsequent functions defined by git. To see common functions available, just type git in the terminal and press enter

| Command | Function |
| ------ | ------ |
| git clone | Creates a folder with the same name as the repo (repository) and copies the contents of the repo there. Also sets up settings to push and pull to the remote (server). |
| git status | These are our eyes. Gives an overview of which files are modified. Sees which goods are in stock. There are also a lot of tips on commands you can use here. |
| git add filename | Loads the file filename onto the loading dock. Also used to tell git to track new files or folders. |
| git add . | Loads all modified files (in the current folder?) onto the loading dock |
| git commit –m "message" | Loads it into the truck with the note "message" |
| git commit –a –m "message" | For those who are a bit lazy and load the truck without a loading dock |
| git push | Sends the truck to the repository in the cloud (on the internet/github). ONLY SEND WORKING CODE! |
| git pull | Pulls down changes from the central repository (from internet/github). Merges your local repository with the central repository in the cloud. |
| git fetch | Pulls down changes from the central repository but without merging. Placed under branch origin/master, which you can then merge. You must do a pull or fetch to be able to retrieve changes that other people have committed. |
| git diff | Compares different versions of files. See examples below. |
| git diff HEAD~ | Compares HEAD (your latest commit) with the previous commit (~ is pronounced and called "Tilde") |
| git diff HEAD~~ | Compares HEAD (your latest commit) with the doubly previous commit. The more ~, the earlier |
| git diff HEAD^5 | compares HEAD with the commit from five times ago |
| git diff branch1 branch2 file | Compares file between two different branches |
| git reset | Git reset is the opposite of git add, i.e. it deprives a file of its staged state as opposed to git add which gives a staged state". When you have put goods on the loading dock but change your mind and want to take them back, you call git reset. This is so you can make changes to the goods you thought were ready to be sent, but weren't. |
| git reset --hard | Will undo everything that's been done, i.e. restore all changed files to the latest commit. |
| git reset --hard HEAD^ | Resets the latest commit and restores working tree and all pointers (WARNING!) |
| git log | Lists all previous commits and shows who posted them in order; latest first |
| git branch | lists all branches that exist |
| git branch branchname | Creates a new branch called branchname |
| git checkout branchname | Switches from current branch to branchname |
| git checkout –b branchname | Creates a new branch called branchname and switches to it |
| git merge branchname | Merge current branch with branchname |

# 4. Import a set-up project in Eclipse

file → import → expand the "android" folder and click on "Existing Android Code Into Workspace → Select "Root Directory", check the project that appears in the box, press finish.

Coding is done in Eclipse but all contact with the repo on the server should be done through the Terminal (command line).

# 5. FAQ

Why shouldn't I use Github's GUI (Graphic User Interface)?

- Because it doesn't work. It doesn't find changes. Four out of five problems that pop up are due to trying to do something in the GUI that doesn't work. The GUI is only designed for the most common functions and can be tricky if certain commands are used.

- Because the terminal is much cooler

Why do I need a .gitignore?

- A .gitignore file tells git which files should NOT be tracked by the system. It can be good to remove binary files, such as images or word documents (the latter can be tracked with a bit of work). Binary files are something that git can't handle in the same way as pure text documents - every time the file is saved and committed to the system, a copy of the file in question will be created: if you have large files (.psd, .tif etc.) it can make your git project take up a lot of space on the computer (it also takes much longer to download the project). For a java project, for example, it's appropriate to remove all .class files. This is done by adding *.class to the .gitignore file. There are standard sets of these files on github that are pretty good.

Where should I put a .gitignore file?

- A .gitignore file will affect all files and folders that are in the folder where the .gitignore file is located. So put that file in the top folder of your project! A .gitignore file that aims to remove a file type that is added after such files have already been tracked by the system will have no effect - you must then manually tell git to stop tracking those files. [Read more about stopping tracking here].

# 6. Miscellaneous – good to know

| Term | Description |
| ------ | ------ |
| AHEAD | you have one or more commits that the server doesn't have (you're ahead) |
| BEHIND | the server has one/several commits that you don't have (you're behind) |
| DIVERGE | you have a commit that the server doesn't have and the server has a commit that you don't have |
| HEAD | Points to the current position in the database |
| Dirty Workspace | you have made changes that haven't yet been committed to the git database |
| Working Tree | The version of files that are currently loaded |
| .gitignore | A file that specifies which files or file types should not be tracked by git |

# 7. Remaining questions to investigate

- [ ] 1. When do you need to press q? Sometimes the terminal locks up and then the solution is to press q, but when?

# 8. Android programming

- You are not allowed to create a new folder in the res folder.

- Download a suitable .gitignore file and place it in the root of your android project

# 9. But what if you're running Windows?

Are you going against the stream? Are you a bit cooler than everyone else? Do you run Windows? If you answered yes to any (or all) of these questions (especially the last question), read the following:

## Don't use the command prompt

Since the command prompt has no built-in git functionality, it's not very suitable to use. There are also slightly different commands for navigating in the command prompt compared to the terminal etc.

## Use Git Bash

Comes with the git installation and is like a terminal for windows. Most Unix commands work (you can overwrite even more), but it's quite slow to use, which is a bit sad.

## Use powershell

You've probably heard of the command prompt (run: cmd). There's a better "version": (run: powershell). Powershell is even more powerful than the terminal; powershell can do everything .NET can do – i.e. quite a lot.

There's a "plugin" for powershell that integrates git. Check [HERE] to make it work. Need help? Ask Anton.

# 10. Pro Tip

- Sublime text 2 is a fantastic text editor – [check it out!]

- If you use Mac or Linux, fix Zsh and replace the old boring terminal. Link and some explanation [can be found here].

- Add aliases in the terminal for commands you use often – saves time!

# 11. Additional Documentation

- http://git-scm.org: official website for .git

- http://gitref.org: reference for common commands (explained quite simply)

- Intro to .git made by one of the founders of github: [youtube]
