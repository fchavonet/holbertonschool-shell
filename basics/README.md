<img  height="50px" align="right" src="https://apply.holbertonschool.com/holberton-logo.png">

# Shell, basics

## 🎓 Objective

At the end of this project, I had to be able to explain to anyone, without the help of Google :

- What does **RTFM** mean?
- What is the **Shell**?
- What is the difference between a **Terminal** and a **Shell**?
- What is a **Shebang**?
- What is the Shell prompt?
- How to use the history (the basics).
- What do the commands or built-ins `cd`, `pwd`, `ls` do?
- How to navigate the file system.
- What do the commands `ls`, `less`, `file` do ?
- How do you use **options** and **arguments** with commands.
- Understand the `ls` long format and how to display it.
- What are the characteristics of **hidden files** and how to list them.
- What is the difference between a **hard link** and a **symbolic link**?
- What do the commands `cp`, `mv`, `rm`, `mkdir` do.
- What are **wildcards** and how do they work.
- What is an **alias**?
- How to read a **man page**.
- Common shortcuts for Bash.
- What does **LTS** mean?

## 🔨 Tech stack

<p align="left">
    <img src="https://img.shields.io/badge/Shell-000000?logo=powerShell&logoColor=white&style=for-the-badge" alt="Shell badge">
    <img src="https://img.shields.io/badge/UBUNTU-e95420?logo=ubuntu&logoColor=white&style=for-the-badge" alt="Ubuntu badge">
    <img src="https://img.shields.io/badge/VIM-019733?logo=vim&logoColor=white&style=for-the-badge" alt="VIM badge">
<p>

## 📋 Requirements

- Allowed editors: vi, vim, emacs.
- All my scripts will be tested on Ubuntu.
- All my scripts should be exactly two lines long (`wc -l file_name` should print 2).
- All my files should end with a new line (why?).
- The first line of all my files should be exactly `#!/bin/bash`.
- I am not allowed to use backticks, `&&`, `||` or `;`.
- All my scripts must be executable.

## 📝 Instruction

<details>
	<summary>
		<b>Task 0. Where am I?</b>
	</summary>
<br>
Write a script that prints the absolute path name of the current working directory.
<br><br>
Example:
<br><br>
	
```
$ ./0-current_working_directory
/basics
$
```
##
Repo:

- GitHub repository: holbertonschool-shell
- Directory: basics
- File: 0-current_working_directory
</details>

<details>
	<summary>
		<b>Task 1. What’s in there?</b>
	</summary>
<br>
Display the contents list of your current directory.
<br><br>
Example:
<br><br>

```
$ ./1-listit
Applications    Documents   Dropbox Movies Pictures
Desktop Downloads   Library Music Public
$
```
##
Repo:

- GitHub repository: holbertonschool-shell
- Directory: basics
- File: 1-listit
</details>

<details>
	<summary>
		<b>Task 2. There is no place like home</b>
	</summary>
<br>
Write a script that changes the working directory to the user’s home directory.
- You are not allowed to use any shell variables
<br><br>
	
```
julien@ubuntu:/tmp$ pwd
/tmp
julien@ubuntu:/tmp$ echo $HOME
/home/julien
julien@ubuntu:/tmp$ source ./2-bring_me_home
julien@ubuntu:~$ pwd
/home/julien
julien@ubuntu:~$ 
```
##
Repo:
- GitHub repository: holbertonschool-shell
- Directory: basics
- File: 2-bring_me_home

## 📂 Files description

| **FILE** | **DESCRIPTION** |
| :-----: | ----- |
| `0-current_working_directory` | |
| `1-listit` | |
| `2-bring_me_home` | |
| `3-listfiles` | |
| `4-listmorefiles` | |
| `5-listfilesdigitonly` | |
| `6-firstdirectory` | |
| `7-movethatfile` | |
| `8-firstdelete` | |
| `9-firstdirdeletion` | |
| `9-firstdirdeletion` | |
| `11-lists` | |
| `12-file_type` | |
| `13-symbolic_link` | |
| `14-copy_html` | |
| `15-lets_move` | |
| `16-clean_emacs` | |
| `17-tree` | |
| `README.md` | The readme file you are currently reading 😉. |



## ♥️ Thanks

A big thank you to all my Holberton School peers for their help and support throughout these projects.
