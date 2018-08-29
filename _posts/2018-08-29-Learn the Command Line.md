---
layout: post
title: Learn the Command Line
---


>사이트:  
 > <https://www.codecademy.com/learn/learn-the-command-line>  
 > <https://www.codecademy.com/articles/command-line-commands>

<br/>

### 1. Navigating the File System

* `pwd`: outputs the name of the current working directory.  
* `ls`: lists all files and directories in the working directory.  
  * 'ls -a' : lists all contents, including hidden files and directories  
  * 'ls -l' : lists all contents of a directory in long format  
  * 'ls -t' : order files and directories by the time they were last modified.  
  * Multiple options can be used together, like 'ls -alt'   
* `cd`: switches you into the directory you specify.  
* `mkdir`: creates a new directory in the working directory.  
* `touch`: creates a new file inside the working directory.   

<br/>

### 2. Viewing and Changing the File System  
* `cp`: copies files
* `mv`: moves and renames files
* `rm`: removes files
  * `rm -r`: removes directories

 <br/>
 
### 3. Redirecting Input and Output 
  * `echo`
    ```
    $ echo "Hello" > hello.txt
     ```
    The echo command accepts the string "Hello" as standard input, and echoes the string "Hello" back to the terminal as standard output.  
    The `>` command redirects the standard output to a file. Here, "Hello" is entered as the standard input. The standard output "Hello" is redirected by `>` to the file hello.txt.
  
  * `cat`: command outputs the contents of a file to the terminal. When you type cat hello.txt, the contents of hello.txt are displayed.
    ```
    $ cat oceans.txt > continents.txt
    ```
     #### The common redirection commands are:
    * `>`: takes the standard output of the command on the left, and redirects it to the file on the right.
    * `>>`: takes the standard output of the command on the left and appends (adds) it to the file on the right.  

       ```
        $  cat glaciers.txt >> rivers.txt
        ```
    * `<`: redirects standard input to a command.  
    * `|`: is a "pipe". The `|` takes the standard output of the command on the left, and pipes it as standard input to the command on the right.  
      ```
      $ cat volcanoes.txt | wc
      ```
      cf.) in turn, the `wc` command outputs the number of lines, words, and characters in volcanoes.txt, respectively.
        
  #### A number of other commands are powerful when combined with redirection commands:
  
  * `sort`: lines of text alphabetically. 
  
  * `uniq` filters duplicate, adjacent lines of text.  
  
  * `grep`:searches for a text pattern and outputs it.  
    ```
    $ grep Mount mountains.txt
    ```
    * `grep -i`: enables the command to be case insensitive. Here, grep searches for capital or lowercase strings that match text in file.
    * `grep -R`: searches all files in a directory and outputs filenames and lines containing matched results.
      ```
      grep -R Arctic /home/ccuser/workspace/geography
      ```
     * `grep -Rl`: searches all files in a directory and outputs only filenames with matched results.
  * `sed`: searches for a text pattern, modifies it, and outputs it.  
      ```
    $ sed 's/snow/rain/' forests.txt
    ```
    * `s`: stands for "substitution". it is always used when using sed for substitution.  
    * `snow`: the search string, the text to find.  
    * `rain`: the replacement string, the text to add in place.  
    ```
    $ sed 's/snow/rain/g' forests.txt
    ```
    * `g`: expression, meaning "global". globally. All instances of "snow" on a line will be turned to "rain".

 <br/>
 
### 4. Enumerating objects  

* The environment refers to the preferences and settings of the current user.  
* The nano editor is a command line text editor used to configure the environment.  

* `~/.bash_profile` is where environment settings are stored. You can edit this file with nano.  

* environment variables are variables that can be used across commands and programs and hold information about the environment.  

  * `export VARIABLE="Value"` sets and exports an environment variable.  
  * `USER` is the name of the current user.  
  * `PS1` is the command prompt.  
  * `HOME` is the home directory. It is usually not customized.  
  * `PATH` returns a colon separated list of file paths. It is customized in advanced cases.  
  * `env` returns a list of environment variables.  


*** 

ex.)

```
nano hello.txt
```
```
"Hello, I am nano."
```
1. The command nano hello.txt opens a new text file named hello.txt in the nano text editor.  
1. "Hello, I am nano" is a text string entered in nano through the cursor.  
1. The menu of keyboard commands at the bottom of the window allow us to save changes to hello.txt and exit nano. The ^ stands for the Ctrl key.  

* Ctrl + O: saves a file. 'O' stands for output.
* Ctrl + X: exits the nano program. 'X' stands for exit.
* Ctrl + G: opens a help menu.
* clear: clears the terminal window, moving the command prompt to the top of the screen.

```
$ nano ~/.bash_profile
```

~/.bash_profile is the name of file used to store environment settings. It is commonly called the "bash profile". When a session starts, it will load the contents of the bash profile before executing commands.  

* The `~` represents the user's home directory.  
* The `.` indicates a hidden file.  
* The name ~/.bash_profile is important, since this is how the command line recognizes the bash profile.  
1. The command `nano ~/.bash_profile` opens up ~/.bash_profile in nano.  
1. The text `echo "Welcome, Jane Doe"` creates a greeting in the bash profile, which is saved. It tells the command line to echo the string "Welcome, Jane Doe" when a terminal session begins.  
1. The command `source ~/.bash_profile` activates the changes in ~/.bash_profile for the current session. Instead of closing the terminal and needing to start a new session, source makes the changes available right away in the session we are in.  

```
alias pd="pwd"
```
The alias command allows you to create keyboard shortcuts, or aliases, for commonly used commands.  

1. Here alias pd="pwd" creates the alias pd for the pwd command, which is then saved in the bash profile. Each time you enter pd, the output will be the same as the pwd command.  
1. The command source ~/.bash_profile makes the alias pd available in the current session.  
1. Each time we open up the terminal, we can use the pd alias.  
 
```
export USER="Jane Doe"
```
environment variables are variables that can be used across commands and programs and hold information about the environment.  

1. The line USER="Jane Doe" sets the environment variable USER to a name "Jane Doe". Usually the USER variable is set to the name of the computer's owner.  
1. The line export makes the variable to be available to all child sessions initiated from the session you are in. This is a way to make the variable persist across programs.  
1. At the command line, the command echo $USER returns the value of the variable. Note that $ is always used when returning a variable's value. Here, the command echo $USER returns the name set for the variable.  

```
export PS1=">> "
```
PS1 is a variable that defines the makeup and style of the command prompt.  

1. export PS1=">> " sets the command prompt variable and exports the variable. Here we change the default command prompt from $ to >>.  
1. After using the source command, the command line displays the new command prompt.  

```
$ echo $HOME
```
The HOME variable is an environment variable that displays the path of the home directory. Here by typing echo $HOME, the terminal displays the path /home/ccuser as output.  

You can customize the HOME variable if needed, but in most cases this is not necessary.  

```
$ echo $PATH
```
PATH is an environment variable that stores a list of directories separated by a colon. Looking carefully, echo $PATH lists the following directories:  

```
/bin/pwd
```
```
/bin/ls
```
```
env
```
The env command stands for "environment", and returns a list of the environment variables for the current user. Here, the env command returns a number of variables, including PATH, PWD, PS1, and HOME.  
```
env | grep PATH
```
env | grep PATH is a command that displays the value of a single environment variable. Here the standard output of env is "piped" to the grep command. grep searches for the value of the variable PATH and outputs it to the terminal.  




 <br/>
 



 <br/>


## OS/리눅스와 Windows의 Command Line 차이  

---
 
 OS/리눅스 | Windows | 설명 | 예
 ---:|---:|---:|---:
  pwd|cd| |
 ls|dir| | 
 cd|cd| |
 touch|echo $null > filename| |
 cp|copy| |
 mv|move| |
 rm|del |
 rm -r|rmdir /S| |
 
 
 ## 모르는것
 ```
 ls -l | head > list1.txt
 ```
In one command, pipe the ls -l command to the head command. Then redirect the standard output of the head command to list1.txt.











