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

<details>
	<summary>
		<b>Task 5. Execute</b>
	</summary>
	<br>

Write a script that adds execute permission to the owner of the file `hello`.
- The file `hello` will be in the working directory.
```julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:26 5-execute
-rw-rw-r-- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
julien@ubuntu:/tmp/h$ ./5-execute 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:26 5-execute
-rwxrw-r-- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 

```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `5-execute`.
<hr>
</details>

<details>
	<summary>
		<b>Task 6. Multiple permissions</b>
	</summary>
	<br>

Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file `hello`.
- The file `hello` will be in the working directory.
```
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 36 Sep 20 14:31 6-multiple_permissions
-rw-r----- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./6-multiple_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 36 Sep 20 14:31 6-multiple_permissions
-rwxr-xr-- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `6-multiple_permissions`.
<hr>
</details>

<details>
	<summary>
		<b>Task 7. Everybody!</b>
	</summary>
	<br

Write a script that adds execution permission to the owner, the group owner and the other users, to the file `hello`.
- The file `hello` will be in the working directory.
- You are not allowed to use commas for this script.
```
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:35 7-everybody
-rw-r----- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./7-everybody 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:35 7-everybody
-rwxr-x--x 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `7-everybody`.
<hr>
</details>

<details>
	<summary>
		<b>Task 8. James Bond</b>
	</summary>
	<br

Write a script that sets the permission to the file `hello` as follows:
- Owner: no permission at all.
- Group: no permission at all.
- Other users: all the permissions.
The file `hello` will be in the working directory You are not allowed to use commas for this script.
```
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:40 8-James_Bond
-rwxr-x--x 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./8-James_Bond 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:40 8-James_Bond
-------rwx 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `8-James_Bond`.
<hr>
</details>

<details>
	<summary>
		<b>Task 9. John Doe</b>
	</summary>
	<br

Write a script that sets the mode of the file `hello` to this:
```
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
```
- The file `hello` will be in the working directory.
- You are not allowed to use commas for this script.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `9-John_Doe`.
<hr>
</details>

<details>
	<summary>
		<b>Task 10. Look in the mirror</b>
	</summary>
	<br

Write a script that sets the mode of the file `hello` the same as `olleh`’s mode.
- The file `hello` will be in the working directory.
- The file `olleh` will be in the working directory.
```
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 42 Sep 20 14:45 10-mirror_permissions
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  0 Sep 20 14:43 olleh
julien@ubuntu:/tmp/h$ ./10-mirror_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 42 Sep 20 14:45 10-mirror_permissions
-rw-rw-r-- 1 julien julien 23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  0 Sep 20 14:43 olleh
julien@ubuntu:/tmp/h$
```
Note: the mode of `olleh` will not always be 664. Make sure your script works for any mode.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `10-mirror_permissions`.
<hr>
</details>

<details>
	<summary>
		<b>Task 11. Directories</b>
	</summary>
	<br

Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users. Regular files should not be changed.
```
julien@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 julien julien   24 Sep 20 14:53 11-directories_permissions
drwx------ 2 julien julien 4096 Sep 20 14:49 dir0
drwx------ 2 julien julien 4096 Sep 20 14:49 dir1
drwx------ 2 julien julien 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./11-directories_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 julien julien   24 Sep 20 14:53 11-directories_permissions
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `11-directories_permissions`.
<hr>
</details>

<details>
	<summary>
		<b>Task 12. More directories</b>
	</summary>
	<br

 Create a script that creates a directory called `my_dir` with permissions 751 in the working directory.
```
julien@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 julien julien   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./12-directory_permission s
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `12-directory_permissions`.
<hr>
</details>

<details>
	<summary>
		<b>Task 13. Change group</b>
	</summary>
	<br

Write a script that changes the group owner to `school` for the file `hello`.
- The file `hello` will be in the working directory.
```
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien   34 Sep 20 15:03 13-change_group
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ sudo ./13-change_group 
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien      34 Sep 20 15:03 13-change_group
drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien    4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien school   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `13-change_group`.
<hr>
</details>

<details>
	<summary>
		<b>Task 14. Owner and group</b>
	</summary>
	<br

Write a script that changes the owner to `vincent` and the group owner to `staff` for all the files and directories in the working directory.
```
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien   36 Sep 20 15:06 14-change_owner_and_group
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ sudo ./14-change_owner_and_group 
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 14-change_owner_and_group
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `14-change_owner_and_group`.
<hr>
</details>

<details>
	<summary>
		<b>Task 15. Symbolic links</b>
	</summary>
	<br

Write a script that changes the owner and the group owner of `_hello` to `vincent` and `staff` respectively.
- The file `_hello` is in the working directory.
- The file `_hello` is a symbolic link.
```
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien   44 Sep 20 15:12 15-symbolic_link_permissions
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
lrwxrwxrwx 1 julien julien    5 Sep 20 15:10 _hello -> hello
julien@ubuntu:/tmp/h$ sudo ./15-symbolic_link_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien      44 Sep 20 15:12 15-symbolic_link_permissions
-rw-rw-r-- 1 julien julien      23 Sep 20 14:25 hello
lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `15-symbolic_link_permissions`.
<hr>
</details>

<details>
	<summary>
		<b>Task 16. If only</b>
	</summary>
	<br

Write a script that changes the owner of the file `hello` to `vincent` only if it is owned by the user `guillaume`.
- The file `hello` will be in the working directory.
```
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien    julien      47 Sep 20 15:18 16-if_only 
-rw-rw-r-- 1 guillaume julien      23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ sudo ./16-if_only 
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien      47 Sep 20 15:18 16-if_only 
-rw-rw-r-- 1 vincent  julien      23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `permissions`.
- File: `16-if_only`.
<hr>
</details>

## 📂 Files description

| **FILE** | **DESCRIPTION** |
| :-----: | ----- |
| `0-iam_betty` | Script to switch the current user to the user `betty`. |
| `1-who_am_i` | Script to print the effective username of the current user. |
| `2-groups` | Script to print all the groups the current user is part of. |
| `3-new_owner` | Script to change the owner of the file `hello` to the user `betty`. |
| `4-empty` | Script to create an empty file called `hello`. |
| `5-execute` | Script to add execute permission to the owner of the file `hello` |
| `6-multiple_permissions` | Script to add execute permission to the owner and the group owner, and read permission to other users, to the file `hello`. |
| `7-everybody` | Script to add execution permission to the owner, the group owner, and other users, to the file `hello`. |
| `8-James_Bond` | Script to set the permissions to the file `hello` as follows: Owner has no permission, Group has no permission, and Other users have all permissions. |
| `9-John_Doe` | Script to set the mode of the file `hello` to a specific pattern. |
| `10-mirror_permissions` | Script to set the mode of the file `hello` the same as the mode of `olleh`. |
| `11-directories_permissions` | Script to add execute permission to all subdirectories of the current directory for the owner, the group owner, and all other users. |
| `12-directory_permissions` | Script to create a directory called `my_dir` with permissions 751 in the working directory. |
| `13-change_group` | Script to change the group owner of the file `hello` to `school`. |
| `14-change_owner_and_group` | Script to change the owner to `vincent` and the group owner to `staff` for all files and directories in the working directory. |
| `15-symbolic_link_permissions` | Script to change the owner and the group owner of `_hello` to `vincent` and `staff` respectively. `_hello` is a symbolic link. |
| `16-if_only` | Script to change the owner of the file `hello` to `vincent` only if it is currently owned by the user `guillaume`. |
| `README.md` | The readme file you are currently reading 😉. |



## ♥️ Thanks

A big thank you to all my Holberton School peers for their help and support throughout these projects.
