# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
```
/c/Users/John Meyer/wats1030-intro-to-unix
```
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
```
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md
```
```
I see files within the repo for this project
```
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
```
total 94K
drwxr-xr-x 1 John Meyer 197121    0 Jan 17 17:01 .
drwxr-xr-x 1 John Meyer 197121    0 Jan 19 15:01 ..
drwxr-xr-x 1 John Meyer 197121    0 Jan 17 17:01 .git
drwxr-xr-x 1 John Meyer 197121    0 Jan 17 17:01 challenge_files
-rw-r--r-- 1 John Meyer 197121 1.1K Jan 17 17:01 LICENSE
-rw-r--r-- 1 John Meyer 197121 5.5K Jan 17 17:01 nix_scavenger_hunt.md
-rw-r--r-- 1 John Meyer 197121  325 Jan 17 17:01 nix_scavenger_hunt_stretch.md
-rw-r--r-- 1 John Meyer 197121 2.8K Jan 17 17:01 README.md
-rw-r--r-- 1 John Meyer 197121  268 Jan 17 17:01 super_scavengers.md
```
```
-alh appears to have listed the same content as ls but with a more verbose readable format includng file details and permmisions
```
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
```
The manual describes the ls options as follows: 
-a lists all entries including those preceded by a .
-l lists entiries in a long form format
-h lists entries and file sizes in a human readable format
```
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
```
bin  cmd  dev  etc  git-bash.exe  git-cmd.exe  LICENSE.txt  mingw64  proc  ReleaseNotes.html  tmp  unins000.dat  unins000.exe  unins000.msg  usr
```
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
```
/
```
```
If / represents the root then there should be nothing more than a / to represent that it is above the drives.
```
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
```
/c/Users/John Meyer
```
```
This would be my user account that is within users and my disk drive or the root for everything that user does
```
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
```
2015_special_stuff.demo  cloaked-wookie.demo  scooter-double-mamba.demo
```
```
I found these 3 files that end in .demo. I used ls *.demo to list all files with .demo.
```
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
```
/c/Users/John Meyer/wats1030-intro-to-unix
```
```
I used cd ../ to move up a directory from the challenge_files child folder
```
* Press the up arrow on your keyboard. *What just happened?*
```
Pressing the up arrow brings up my last command used in this case pwd which showed the result of cd ../
```
* Press the up arrow a few more times. *What do you see?*
```
It brings up the last commands I used in order
```
* Run the `history` command. *What do you see?*
```
History brings up all the commands I have used since my last pull request including git and failed commands
```
### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
```
John Meyer
```
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
```
Both of my machines only have one user thus `who` didn't print anything
```
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
```
I wasn't able to get uptime to run on my windows machines via git bash but I found a linux evironment online that 
showed me what the results would be formatted as: 00:58:23 up 46 min, 1 users, load average: 1.31, 1.43, 0.88
```
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
```
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
     8692    3528    8692      10704  cons0     197609 17:05:38 /usr/bin/ps
     3528       1    3528       3528  cons0     197609 23:15:22 /usr/bin/bash
```
```
This is a list of running processes in my system memory. The first few columns are IDs of the process, the terminal that ran it, and a user id. The time it was initialized and the name of the command.
```
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
```
This shows what processes are using the most resources and how those resources are distributed.
```
### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
```
credit_cards.txt  credit_cards2.txt
```
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
```
01-15-2015
```
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
```
/c/Users/John Meyer/wats1030-intro-to-unix/challenge_files/tmp/modi_laboriosam.txt
```
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
```
I could not get the syntax of grep to work. I dont understand a single resource I've looked at.
```

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
```
I cannot complete this section with git bash. Every command does not give a result.
```