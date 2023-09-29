<img  height="50px" align="right" src="https://apply.holbertonschool.com/holberton-logo.png">

# Shell, permissions

## 🎓 Objective

At the end of this project, I had to be able to explain to anyone, without the help of Google :

- What do the commands `chmod`, `sudo`, `su`, `chown`, `chgrp` do?
- How to represent each of the three sets of permissions (owner, group, and other) as a single digit.
- How to change permissions, owner and group of a file.
- Why can’t a normal user chown a file?
- How to run a command with root privileges.
- How to change user ID or become superuser.
- How to create a user.
- How to create a group.
- How to print real and effective user and group IDs.
- How to print the groups a user is in.
- How to print the effective userid.

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
		<b>Task 0. My name is Betty</b>
	</summary>
	<br>

Create a script that switches the current user to the user `betty`.
- You should use exactly 8 characters for your command (+1 character for the new line).
- You can assume that the user betty will exist when we will run your script.

```
julien@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
julien@ubuntu:/tmp/h$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `0-iam_betty`.
<hr>
</details>

<details>
	<summary>
		<b>Task 1. Who am I</b>
	</summary>
	<br>

Write a script that prints the effective username of the current user.
```
julien@ubuntu:/tmp/h$ ./1-who_am_i
julien
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `1-who_am_i`.
<hr>
</details>

<details>
	<summary>
		<b>Task 2. Groups</b>
	</summary>
	<br>

Write a script that prints all the groups the current user is part of.
```
julien@ubuntu:/tmp/h$ ./2-groups
julien adm cdrom sudo dip plugdev lpadmin sambashare
julien@ubuntu:/tmp/h$ 
```
Note: depending on the user, you will get a different output.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `2-groups`.
<hr>
</details>

<details>
	<summary>
		<b>Task 3. New owner</b>
	</summary>
	<br>

Write a script that changes the owner of the file `hello` to the user `betty`.
```
julien@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 julien julien 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 julien julien  0 Sep 20 14:18 hello
julien@ubuntu:/tmp/h$ sudo ./3-new_owner 
julien@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 julien julien 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 betty  julien  0 Sep 20 14:18 hello
julien@ubuntu:/tmp/h$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `3-new_owner`.
<hr>
</details>

<details>
	<summary>
		<b>Task 4. Empty!</b>
	</summary>
	<br>

Write a script that creates an empty file called `hello`.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `4-empty`.
<hr>
</details>

## 📂 Files description

| **FILE** | **DESCRIPTION** |
| :-----: | ----- |
| `0-iam_betty` | |
| `1-who_am_i` | |
| `2-groups` | |
| `3-new_owner` | |
| `4-empty` | |
| `5-execute` | |
| `6-multiple_permissions` | |
| `7-everybody` | |
| `8-James_Bond` | |
| `9-John_Doe` | |
| `10-mirror_permissions` | |
| `11-directories_permissions` | |
| `12-directory_permissions` | |
| `13-change_group` | |
| `14-change_owner_and_group` | |
| `15-symbolic_link_permissions` | |
| `16-if_only` | |
| `README.md` | The readme file you are currently reading 😉. |



## ♥️ Thanks

A big thank you to all my Holberton School peers for their help and support throughout these projects.
