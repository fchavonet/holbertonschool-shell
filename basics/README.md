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

### <span id="mandatory-tasks">Mandatory tasks</span>

<details>
	<summary>
		<b>Task 0. Where am I?</b>
	</summary>
	<br>

Write a script that prints the absolute path name of the current working directory.

Example:
```
$ ./0-current_working_directory
/basics
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `0-current_working_directory`.
<hr>
</details>

<details>
	<summary>
		<b>Task 1. What’s in there?</b>
	</summary>
	<br>

Display the contents list of your current directory.

Example:
```
$ ./1-listit
Applications    Documents   Dropbox Movies Pictures
Desktop Downloads   Library Music Public
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `1-listit`.
<hr>
</details>

<details>
	<summary>
		<b>Task 2. There is no place like home</b>
	</summary>
	<br>

Write a script that changes the working directory to the user’s home directory.
- You are not allowed to use any shell variables.
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
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `2-bring_me_home`.
<hr>
</details>

<details>
	<summary>
		<b>Task 3. The long format</b>
	</summary>
	<br>

Display current directory contents in a long format

Example:
```
$ ./3-listfiles
total 40
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `3-listfiles`.
<hr>
</details>

<details>
	<summary>
		<b>Task 4. Hidden files</b>
	</summary>
	<br>
	
Display current directory contents, including hidden files (starting with `.`).
Use the long format.

Example:
```
$ ./4-listmorefiles
total 48
drwxr-xr-x@ 6 sylvain staff 204 Jan 25 00:29 .
drwxr-xr-x@ 43 sylvain staff 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:41 4-listmorefiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `4-listmorefiles`.
<hr>
</details>

<details>
	<summary>
		<b>Task 5. I love numbers</b>
	</summary>
	<br>

Display current directory contents.
- Long format.
- With user and group IDs displayed numerically.
- And hidden files (starting with `.`).

Example:
```
$ ./5-listfilesdigitonly
total 56
drwxr-xr-x@ 6 501 20 204 Jan 25 00:29 .
drwxr-xr-x@ 43 501 20 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:23 1-listfiles
-rwxr-xr-x@ 1 501 20 19 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 501 20 20 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:41 4-listmorefiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:43 5-listfilesdigitonly
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:20 README.md
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `5-listfilesdigitonly`.
<hr>
</details>

<details>
	<summary>
		<b>Task 6. Welcome</b>
	</summary>
	<br>

Create a script that creates a directory named `my_first_directory` in the `/tmp/` directory.

Example:
```
$ ./6-firstdirectory
$ file /tmp/my_first_directory/
/tmp/my_first_directory/: directory
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `6-firstdirectory`.
<hr>
</details>

<details>
	<summary>
		<b>Task 7. Betty in my first directory</b>
	</summary>
	<br>

Move the file betty from `/tmp/` to `/tmp/my_first_directory`.

Example:
```
$ ./7-movethatfile
$ ls /tmp/my_first_directory/
betty
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `7-movethatfile`.
<hr>
</details>

<details>
	<summary>
		<b>Task 8. Bye bye Betty</b>
	</summary>
	<br>

Delete the file `betty`.
- The file betty is in `/tmp/my_first_directory`

Example:
```
 ./8-firstdelete
$ ls /tmp/my_first_directory/
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `8-firstdelete`.
<hr>
</details>

<details>
	<summary>
		<b>Task 9. Bye bye My first directory</b>
	</summary>
	<br>

Delete the directory `my_first_directory` that is in the `/tmp` directory.

Example:
```
$ ./9-firstdirdeletion
$ file /tmp/my_first_directory
/tmp/my_first_directory: cannot open `/tmp/my_first_directory' (No such file or directory)
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `9-firstdirdeletion`.
<hr>
</details>

<details>
	<summary>
		<b>Task 10. Back to the future</b>
	</summary>
	<br>

Write a script that changes the working directory to the previous one.
```
julien@ubuntu:/tmp$ pwd
/tmp
julien@ubuntu:/tmp$ cd /var
julien@ubuntu:/var$ pwd
/var
julien@ubuntu:/var$ source ./10-back
/tmp
julien@ubuntu:/tmp$ pwd
/tmp
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `10-back`.
<hr>
</details>

<details>
	<summary>
		<b>Task 11. Lists</b>
	</summary>
	<br>

Write a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the `/boot` directory (in this order), in long format.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `11-lists`.
<hr>
</details>

<details>
	<summary>
		<b>Task 12. File type</b>
	</summary>
	<br>

Write a script that prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.

Example:
```
ubuntu@ip-172-31-63-244:~$ ./12-file_type
/tmp/iamafile: ELF 64-bit LSB  executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.24, BuildID[sha1]=bd39c07194a778ccc066fc963ca152bdfaa3f971, stripped
```
Note that depending on the file, the output of your script will be different.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `12-file_type`.
<hr>
</details>

<details>
	<summary>
		<b>Task 13. We are symbols, and inhabit symbols</b>
	</summary>
	<br>

Create a symbolic link to `/bin/ls`, `named __ls__`. The symbolic link should be created in the current working directory.
```
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
ubuntu@ip-172-31-63-244:/tmp/sym$./13-symbolic_link
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `13-symbolic_link`.
<hr>
</details>

<details>
	<summary>
		<b>Task 14. Copy HTML files</b>
	</summary>
	<br>

Create a script that copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.

You can consider that all HTML files have the extension `.html`
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `14-copy_html`.
<hr>
</details>

<details>
	<summary>
		<b>Task 15. Let’s move</b>
	</summary>
	<br>

Create a script that moves all files beginning with an uppercase letter to the directory `/tmp/u`.

You can assume that the directory `/tmp/u` will exist when we will run your script
```
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 My_file
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 Elif_ym
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
ubuntu@ip-172-31-63-244:/tmp/sym$ ./15-lets_move
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 My_file
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 Elif_ym
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`
- Directory: `basics`.
- File: `15-lets_move`.
<hr>
</details>

<details>
	<summary>
		<b>Task 16. Clean Emacs</b>
	</summary>
	<br>

Create a script that deletes all files in the current working directory that end with the character `~`.
```
ubuntu@ip-172-31-63-244:/tmp/sym$ ls
main.c  main.c~  Makefile~
ubuntu@ip-172-31-63-244:/tmp/sym$ ./16-clean_emacs
ubuntu@ip-172-31-63-244:/tmp/emacs$ ls
main.c
ubuntu@ip-172-31-63-244:/tmp/emacs$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `16-clean_emacs`.
<hr>
</details>

<details>
	<summary>
		<b>Task 17. Tree</b>
	</summary>
	<br>

Create a script that creates the directories `welcome/`, `welcome/to/` and `welcome/to/school` in the current directory.

You are only allowed to use two spaces (and lines) in your script, not more.
```
julien@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 julien julien 44 Sep 20 12:09 17-tree
julien@ubuntu:/tmp/h$ wc -l 17-tree 
2 17-tree
julien@ubuntu:/tmp/h$ head -1 17-tree 
#!/bin/bash
julien@ubuntu:/tmp/h$ tr -cd ' ' < 17-tree | wc -c # you do not have to understand this yet, but the result should be 2, 1 or 0
2
julien@ubuntu:/tmp/h$ ./17-tree 
julien@ubuntu:/tmp/h$ ls
17-tree  welcome
julien@ubuntu:/tmp/h$ ls welcome/
to
julien@ubuntu:/tmp/h$ ls -l welcome/to
total 4
drwxrwxr-x 2 julien julien 4096 Sep 20 12:11 school
julien@ubuntu:/tmp/h$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `basics`.
- File: `17-tree`.
<hr>
</details>

## 📂 Files description

| **FILE** | **DESCRIPTION** |
| :-----: | ----- |
| `0-current_working_directory` | Script to print the absolute path name of the current working directory. |
| `1-listit` | Script to display the contents list of the current directory. |
| `2-bring_me_home` | Script to change the working directory to the user's home directory. |
| `3-listfiles` |  Script to display current directory contents in a long format. |
| `4-listmorefiles` | Script to display current directory contents, including hidden files, in long format. |
| `5-listfilesdigitonly` | Script to display current directory contents in long format with user and group IDs displayed numerically, including hidden files. |
| `6-firstdirectory` | Script to create a directory named `my_first_directory` in the `/tmp/` directory. |
| `7-movethatfile` | Script to move the file betty from `/tmp/` to `/tmp/my_first_directory`. |
| `8-firstdelete` | Script to delete the file betty in `/tmp/my_first_directory`. |
| `9-firstdirdeletion` | Script to delete the directory `my_first_directory` in the `/tmp` directory.|
| `10-back` | Script to change the working directory to the previous one. |
| `11-lists` | Script to list all files in the current directory, the parent directory, and the `/boot` directory in long format. |
| `12-file_type` | Script to print the type of the file named iamafile in the `/tmp` directory. |
| `13-symbolic_link` | Script to create a symbolic link named `__ls__` to `/bin/ls` in the current working directory. |
| `14-copy_html` | Script to copy HTML files from the current working directory to the parent directory if they don't exist or are newer. |
| `15-lets_move` | Script to move files beginning with an uppercase letter to the directory `/tmp/u|` |
| `16-clean_emacs` | Script to delete files in the current working directory that end with the character `~` |
| `17-tree` | Script to create directories `welcome/`, `welcome/to/`, and `welcome/to/school` in the current directory. |
| `README.md` | The readme file you are currently reading 😉. |



## ♥️ Thanks

A big thank you to all my Holberton School peers for their help and support throughout these projects.
