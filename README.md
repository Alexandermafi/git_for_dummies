# Git for Dummies

A guide on how to use Git in the command line (e.g. Terminal). Commands in Git and the command line will be explained and presented to provide insight into what can be done. The guide will use a factory metaphor to understand git from perhaps a more familiar perspective. 

[1. Factory Metaphor]

[2. Unix Commands (a selection)]

[3. Git commands]

[4. FAQ]

[5. Miscellaneous - good to know + glossary]

[6.  When the Terminal Locks Up - Press Q or "ctrl + c" to get Out]

[7. But what if you're running Windows?]

[8. Pro Tip]

[9. Additional Documentation]

[1. Factory Metaphor]:https://github.com/Alexandermafi/git_for_dummies#1-factory-metaphor
[2. Unix Commands (a selection)]:https://github.com/Alexandermafi/git_for_dummies#2-unix-commands-a-selection
[3. Git commands]:https://github.com/Alexandermafi/git_for_dummies#3-git-commands
[4. FAQ]:https://github.com/Alexandermafi/git_for_dummies#5-faq
[5. Miscellaneous - good to know + glossary]:https://github.com/Alexandermafi/git_for_dummies#6-Miscellaneous--good-to-know
[6.  When the Terminal Locks Up - Press Q or "ctrl + c" to get Out]:https://github.com/Alexandermafi/git_for_dummies#7-When-the-Terminal-Locks-Up---Press-Q-or-ctrl-+-c-to-get-Out
[7. But what if you're running Windows?]:https://github.com/Alexandermafi/git_for_dummies#9-But-what-if-you-re-running-Windows
[8. Pro Tip]:https://github.com/Alexandermafi/git_for_dummies#10-pro-tip
[9. Additional Documentation]:https://github.com/Alexandermafi/git_for_dummies#11-Additional-Documentation


# 1. Factory Metaphor

Metaphor concepts used: Inventory, loading dock, trucks shipping goods

- git status -> Lets you see what goods you have in your inventory

- git add -> Loads the goods onto your loading dock

- git commit -m "message" -> Loads the goods into the truck. The goods are marked with the note "message"

- git push -> Sends the truck to the recipient

- git pull -> Receives a truck full of goods that are put into your inventory

- git fetch -> Receives a truck full of goods but does NOT put them into your inventory

# 2. Unix Commands (a selection)

Basic Unix commands for file and folder manipulation that work in the command line (e.g. Terminal). More details here: https://www.oliverelliott.org/article/computing/tut_unix/#100UsefulUnixCommands

Mac and Linux are unix-like systems and therefore unix commands works of the box. 

For Windows the unix commands won't work by default, but you can install The Windows Subsystem for Linux (WSL) to get the same command line experience. Guide: https://learn.microsoft.com/en-us/windows/wsl/install. This allows you to e.g. install Ubuntu on your windows machine. 

It's necessary to learn a few basic operating system concepts like how to operate on files, directories, and file systems with the command line. Since using Git with the command line, relies on the foundation knowledge of using unix commands to manipulate files and folders. 

| Command | Function |
| ------ | ------ |
| cd | changes to your home folder (user) |
| cd ~ | changes to your home folder (user) - notice the command below which does the same thing |
| cd folder1/folder2/folder3 | Changes to folder 3, which is in folder2 etc |
| cd .. | Change directory to one step up |
| touch filename | Creates a new file named filename |
| ls | Shows visible files and folders in the current location |
| ls –a | Shows all (including hidden) files and folders in the current location: -a is called a flag for ls |
| rm filename | deletes the file filename. Doesn't work with folders |
| rm –r foldername | Recursively deletes all contents in a folder |
| rm –rf foldername | Recursively deletes the folder named foldername. rf stands for recursive force which means it doesn't ask for permission when it's unsure, which it can be if something unexpected happens. For example, if there are files in subfolders. This command is specific to Mac (actually unix), on PC it's: rm foldername. VERY POWERFUL, so be careful. E.g., rm-rf * will delete EVERYTHING... |
| nano README.md | Opens the file README.md in the terminal with the nano editor. You can then change the content directly in the terminal. Only applies to UNIX systems. |
| man command | Brings up a detailed description of the command. EX: man cd |
| command --help | Brings up a shorter help for a command. E.g. "git clone --help|
| grep –r searchterm | Searches recursively in ALL FILES for the search term. Very powerful! Can be used with wildcard (*) |
| ctrl + c | Interrupts the current command |

# 3. Git commands

All commands that have to do with git start with git, followed by the command name. This tells the terminal to use git and run the subsequent functions defined by git. To see common functions available, just type git in the terminal and press enter

| Command | Function |
| ------ | ------ |
| git clone | Creates a folder with the same name as the repo (repository) and copies the repo's contents there. It also sets up settings to push and pull to the remote (server). |
| git status | These are our eyes. Gives an overview of which files are modified. Sees which goods are in inventory. There are also a lot of tips on commands you can use here. |
| git add filename | Loads the file filename onto the loading dock. Also used to tell git to track new files or folders. |
| git add . | Loads all modified files (in the current folder and subdirectories) onto the loading dock |
| git commit –m "message" | Loads it into the truck with the note "message" |
| git commit –a –m "message" | For those who are a bit lazy and load the truck without a loading dock. Only works on files that have been explicitly tracked by "git add" before (it stages and commits tracked files only, not new files) |
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
| git merge branchname | Merge current branch with branchname |
| git init | create a new repository in the folder where you stand |
| git rebase | align commit history |
| git revert | undo commits |

The git stash command helps you save modifications that you're not ready to commit yet. Think of it as a temporary drawer where you can store your work-in-progress changes.

| Command | Function |
| ------ | ------ |
| `git stash` | Save your current changes in a temporary storage and revert to the last commit |
| `git stash save "message"` | Same as `git stash` but with a descriptive message |
| `git stash list` | Show all stashed changes |
| `git stash apply` | Apply the most recent stash but keep it in the stash list |
| `git stash pop` | Apply the most recent stash and remove it from the stash list |
| `git stash drop` | Remove the most recent stash |
| `git stash clear` | Remove all stashes |

Using the factory metaphor: Think of stash as a temporary storage room where you can put work-in-progress goods that aren't ready for shipping yet.

# 4. FAQ

Why do I need a .gitignore?

- A .gitignore file tells git which files should NOT be tracked by the system. It can be good to remove binary files, such as images or word documents (the latter can be tracked with a bit of work). Binary files are something that git can't handle in the same way as pure text documents - every time the file is saved and committed to the system, a copy of the file in question will be created: if you have large files (.psd, .tif etc.) it can make your git project take up a lot of space on the computer (it also takes much longer to download the project). For a java project, for example, it's appropriate to remove all .class files. This is done by adding *.class to the .gitignore file. There are standard sets of these files on github that are pretty good.

Where should I put a .gitignore file?

- A .gitignore file will affect all files and folders that are in the folder where the .gitignore file is located. So put that file in the top folder of your project! A .gitignore file that aims to remove a file type that is added after such files have already been tracked by the system will have no effect - you must then manually tell git to stop tracking those files. [Read more about stopping tracking here].

# 5. Miscellaneous – good to know

| Term | Description |
| ------ | ------ |
| AHEAD | you have one or more commits that the server doesn't have (you're ahead) |
| BEHIND | the server has one/several commits that you don't have (you're behind) |
| DIVERGE | you have a commit that the server doesn't have and the server has a commit that you don't have |
| HEAD | Points to the current position in the database (points to the latest commit in the current branch)|
| Dirty Workspace | you have made changes that haven't yet been committed to the git database |
| Working Tree | The version of files that are currently loaded |
| .gitignore | A file that specifies which files or file types should not be tracked by git |



# 6. When the Terminal Locks Up - Press Q or "ctrl + c" to get Out

Terminal Navigation: When to use 'q' vs 'control + c'. Think of 'q' as a gentle exit from a viewing mode, while 'control + c' is an emergency stop button for active processes.

### Press 'q' (quit)
Used when you're in a pager view - a scrollable interface that displays content page by page. You'll typically see a colon ':' at the bottom of the screen.
Common commands that open pager views:

- `git log` - When viewing commit history
- `man` commands - When reading manual pages
- `git diff` - When the diff is longer than your screen height

### Press 'control + c'
Used to interrupt or stop processes. Common scenarios:

Interrupting a running command or process
Exiting out of a "stuck" or hanging operation
Stopping an infinite loop or long-running operation
Canceling an interactive prompt


# 7. But what if I'm running Windows?

Are you going against the stream? Are you a bit cooler than everyone else? Do you run Windows? If you answered yes to any (or all) of these questions (especially the last question), read the following:

### Install The Windows Subsystem for Linux (WSL)
For Windows the unix commands won't work by default, but you can install The Windows Subsystem for Linux (WSL) to get the same command line experience. Guide: https://learn.microsoft.com/en-us/windows/wsl/install. This allows you to e.g. install Ubuntu on your windows machine. 

### Don't use the command prompt

Since the command prompt has no built-in git functionality, it's not very suitable to use. There are also slightly different commands for navigating in the command prompt compared to the terminal etc.

### Use Git Bash

Comes with the git installation and is like a terminal for windows. Most Unix commands work (you can overwrite even more).


# 8. Pro Tip

- VSCode is a great editing text and writing code – [check it out!]

- If you use Mac or Linux, fix Zsh and replace the old boring terminal.Link and some explanation [can be found here].

- Add aliases in the terminal for commands you use often – saves time!

# 9. Additional Documentation

- Git official website: http://git-scm.org
- Youtube - Intro to Git made by a Github founder: https://www.youtube.com/watch?v=ZDR433b0HJY
- Beginner-friendly Git & GitHub course from Google : https://www.coursera.org/learn/introduction-git-github
- [Pro Git](https://git-scm.com/book/en/v2): This book (available online and in print) covers all the fundamentals of how Git works and how to use it. Refer to it if you want to learn more about the subjects that we cover throughout the course.
- [Git tutorial](https://git-scm.com/docs/gittutorial): This tutorial includes a very brief reference of all Git commands available. You can use it to quickly review the commands that you need to use.
- Git game for practice: https://ohmygit.org/
- Additional git course options:
    - https://profy.dev/project/github-minesweeper
    - https://www.theodinproject.com/lessons/foundations-introduction-to-git
- Command line tutorial (needed for file and folder manipulation) options:
    - https://ubuntu.com/tutorials/command-line-for-beginners#1-overview
    - https://www.theodinproject.com/lessons/foundations-command-line-basics
    - Linux Tutorial for Beginners - Learn Linux and the Bash Command Line https://ryanstutorials.net/linuxtutorial/ 

[HERE]:http://haacked.com/archive/2011/12/13/better-git-with-powershell.aspx
[youtube]:http://www.youtube.com/watch?feature=player_detailpage&v=ZDR433b0HJY#t=2791s
[check it out!]: https://code.visualstudio.com
[can be found here]:http://www.maclife.com/article/columns/terminal_101_better_shell_zsh
