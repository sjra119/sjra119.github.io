------
layout: post
title: Learn the Command Line
------

사이트: <https://www.codecademy.com/learn/learn-the-command-line>  
       <https://www.codecademy.com/articles/command-line-commands>

#### 1. Navigating the File System

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

#### 2. Viewing and Changing the File System  
* `cp`: copies files
* `mv`: moves and renames files
* `rm`: removes files
  * `rm -r`: removes directories

 <br/>
 
#### 3. Redirecting Input and Output 
  * `echo`
    ```
    $ echo "Hello" > hello.txt
     ```
    The `>` command redirects the standard output to a file. Here, "Hello" is entered as the standard input. The standard output "Hello" is redirected by `>` to the file hello.txt.
  
  * `cat`: command outputs the contents of a file to the terminal. When you type cat hello.txt, the contents of hello.txt are displayed.
    ```
    $ cat oceans.txt > continents.txt
    ```
     ##### The common redirection commands are:
    * `>`: takes the standard output of the command on the left, and redirects it to the file on the right. Here the standard output of cat oceans.txt is redirected to continents.txt.  
   Note that `>` overwrites all original content in continents.txt.
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
        
##### A number of other commands are powerful when combined with redirection commands:
  
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
 <br/>
 <br/>


# OS/리눅스와 Windows의 Command Line 차이  

---

<br/>
 
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
 
 
