<img  height="50px" align="right" src="https://apply.holbertonschool.com/holberton-logo.png">

# Shell, I/O Redirections and filters

## 🎓 Objective

At the end of this project, I had to be able to explain to anyone, without the help of Google :

- What do the commands `head`, `tail`, `find`, `wc`, `sort`, `uniq`, `grep`, `tr` do?
- How to redirect standard output to a file.
- How to get standard input from a file instead of the keyboard.
- How to send the output from one program to the input of another program.
- How to combine commands and filters with redirections
- What are special characters?
- How to display a line of text.
- How to concatenate files and print on the standard output.
- How to reverse a string.
- How to remove sections from each line of files.
- What is the `/etc/passwd` file and what is its format?
- What is the `/etc/shadow` file and what is its format?

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
		<b>Task 0. Hello World</b>
	</summary>
	<br>

Write a script that prints “Hello, World”, followed by a new line to the standard output.
```
julien@ubuntu:/tmp/h$ ./0-hello_world 
Hello, World
julien@ubuntu:/tmp/h$ ./0-hello_world | cat -e
Hello, World$
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `io_redirections_and_filters`.
- File: `0-hello_world`.
<hr>
</details>

<details>
	<summary>
		<b>Task 1. Confused smiley</b>
	</summary>
	<br>

Write a script that displays a confused smiley `"(Ôo)'`.
```
julien@ubuntu:/tmp/h$ ./1-confused_smiley 
"(Ôo)'
julien@ubuntu:/tmp/h$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `io_redirections_and_filters`.
- File: `1-confused_smiley`.
<hr>
</details>

<details>
	<summary>
		<b>Task 2. Let's display a file</b>
	</summary>
	<br>

Display the content of the `/etc/passwd` file.

Example:
```
$ ./2-hellofile
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
_installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
_lp:*:26:26:Printing Services:/var/spool/cups:/usr/bin/false
_postfix:*:27:27:Postfix Mail Server:/var/spool/postfix:/usr/bin/false
_scsd:*:31:31:Service Configuration Service:/var/empty:/usr/bin/false
_ces:*:32:32:Certificate Enrollment Service:/var/empty:/usr/bin/false
_mcxalr:*:54:54:MCX AppLaunch:/var/empty:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `io_redirections_and_filters`.
- File: `2-hellofile`.
<hr>
</details>

<details>
	<summary>
		<b>Task 3. What about 2?</b>
	</summary>
	<br>

Display the content of `/etc/passwd` and `/etc/hosts`.

Example:
```
$ ./3-twofiles
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting. Do not change this entry.
##
127.0.0.1   localhost
255.255.255.255 broadcasthost
::1 localhost
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `io_redirections_and_filters`.
- File: `3-twofiles`.
<hr>
</details>

<details>
	<summary>
		<b>Task 4. Last lines of a file</b>
	</summary>
	<br>

Display the last 10 lines of `/etc/passwd`.

Example:
```
$ ./4-lastlines
_assetcache:*:235:235:Asset Cache Service:/var/empty:/usr/bin/false
_coremediaiod:*:236:236:Core Media IO Daemon:/var/empty:/usr/bin/false
_launchservicesd:*:239:239:_launchservicesd:/var/empty:/usr/bin/false
_iconservices:*:240:240:IconServices:/var/empty:/usr/bin/false
_distnote:*:241:241:DistNote:/var/empty:/usr/bin/false
_nsurlsessiond:*:242:242:NSURLSession Daemon:/var/db/nsurlsessiond:/usr/bin/false
_nsurlstoraged:*:243:243:NSURLStorage Daemon:/var/empty:/usr/bin/false
_displaypolicyd:*:244:244:Display Policy Daemon:/var/empty:/usr/bin/false
_astris:*:245:245:Astris Services:/var/db/astris:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
```
Tips: “Thinks of it as a cat, what is at the end of it?”
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `io_redirections_and_filters`.
- File: `4-lastlines`.
<hr>
</details>

<details>
	<summary>
		<b>Task 5. I'd prefer the first ones actually</b>
	</summary>
	<br>

Display the first 10 lines of `/etc/passwd`.

Example:
```
$ ./5-firstlines
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `io_redirections_and_filters`.
- File: `5-firstlines`.
<hr>
</details>


## 📂 Files description

| **FILE** | **DESCRIPTION** |
| :-----: | ----- |
| `0-hello_world` | |
| `1-confused_smiley` | |
| `2-hellofile` | |
| `3-twofiles` | |
| `4-lastlines` | |
| `5-firstlines` | |
| `6-third_liney` | |
| `7-file` | |
| `8-cwd_state` | |
| `9-duplicate_last_line` | |
| `10-no_more_js` | |
| `11-directories` | |
| `12-newest_files` | |
| `13-unique` | |
| `14-findthatword` | |
| `15-countthatword` | |
| `16-whatsnext` | |
| `17-hidethisword` | |
| `18-letteronly` | |
| `19-AZ` | |
| `20-hiago` | |
| `21-reverse` | |
| `22-users_and_homes` | |
| `23-empty_casks` | |
| `24-gifs` | |
| `25-acrostic` | |
| `README.md` | The readme file you are currently reading 😉. |



## ♥️ Thanks

A big thank you to all my Holberton School peers for their help and support throughout these projects.
