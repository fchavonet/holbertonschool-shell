<img  height="50px" align="right" src="https://apply.holbertonschool.com/holberton-logo.png">

# Shell, init files, variables and expansions

## 📝 Objective

At the end of this project, I had to be able to explain to anyone, without the help of Google :

- What are the `/etc/profile` file and the `/etc/profile.d` directory?
- What is the `~/.bashrc` file?
- What is the difference between a local and a global variable?
- What is a reserved variable?
- How to create, update and delete shell variables.
- What are the roles of the following reserved variables: HOME, PATH, PS1?
- What are special parameters?
- What is the special parameter `$?`?
- What is expansion and how to use them?
- What is the difference between single and double quotes and how to use them properly?
- How to do command substitution with `$()` and backticks.
- How to perform arithmetic operations with the shell.
- How to create an alias.
- How to list aliases.
- How to temporarily disable an alias.
- How to execute commands from a file in the current shell.

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
		<b>Task 0. < o ></b>
	</summary>
	<br>

Create a script that creates an alias.
- Name: `ls`
- Value: `rm *`
```
julien@ubuntu:/tmp/0x03$ ls
0-alias  file1  file2
julien@ubuntu:/tmp/0x03$ source ./0-alias 
julien@ubuntu:/tmp/0x03$ ls
julien@ubuntu:/tmp/0x03$ \ls
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `0-alias`.
<hr>
</details>

<details>
	<summary>
		<b>Task 1. Hello you</b>
	</summary>
	<br>

Create a script that prints `hello user`, where user is the current Linux user.
```
julien@ubuntu:/tmp/0x03$ id
uid=1000(julien) gid=1000(julien) groups=1000(julien),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),113(lpadmin),128(sambashare)
julien@ubuntu:/tmp/0x03$ ./1-hello_you 
hello julien
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `1-hello_you`.
<hr>
</details>

<details>
	<summary>
		<b>Task 2. The path to success is to take massive, determined action</b>
	</summary>
	<br>

Add `/action` to the `PATH``. `/action` should be the last directory the shell looks into when looking for a program.
```
julien@ubuntu:/tmp/0x03$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
julien@ubuntu:/tmp/0x03$ source ./2-path 
julien@ubuntu:/tmp/0x03$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/action
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `2-path`.
<hr>
</details>

<details>
	<summary>
		<b>Task 3. If the path be beautiful, let us not ask where it leads</b>
	</summary>
	<br>

Create a script that counts the number of directories in the PATH.
```
julien@ubuntu:/tmp/0x03$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
julien@ubuntu:/tmp/0x03$ . ./3-paths 
11
julien@ubuntu:/tmp/0x03$ PATH=/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:::::/hello
julien@ubuntu:/tmp/0x03$ . ./3-paths 
12
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `3-paths`.
<hr>
</details>

<details>
	<summary>
		<b>Task 4. Global variables</b>
	</summary>
	<br>

Create a script that lists environment variables.
```
julien@ubuntu:/tmp/0x03$ source ./4-global_variables
CC=gcc
CDPATH=.:~:/usr/local:/usr:/
CFLAGS=-O2 -fomit-frame-pointer
COLORTERM=gnome-terminal
CXXFLAGS=-O2 -fomit-frame-pointer
DISPLAY=:0
DOMAIN=hq.garrels.be
e=
TOR=vi
FCEDIT=vi
FIGNORE=.o:~
G_BROKEN_FILENAMES=1
GDK_USE_XFT=1
GDMSESSION=Default
GNOME_DESKTOP_SESSION_ID=Default
GTK_RC_FILES=/etc/gtk/gtkrc:/nethome/franky/.gtkrc-1.2-gnome2
GWMCOLOR=darkgreen
GWMTERM=xterm
HISTFILESIZE=5000
history_control=ignoredups
HISTSIZE=2000
HOME=/nethome/franky
HOSTNAME=octarine.hq.garrels.be
INPUTRC=/etc/inputrc
IRCNAME=franky
JAVA_HOME=/usr/java/j2sdk1.4.0
LANG=en_US
LDFLAGS=-s
LD_LIBRARY_PATH=/usr/lib/mozilla:/usr/lib/mozilla/plugins
LESSCHARSET=latin1
LESS=-edfMQ
LESSOPEN=|/usr/bin/lesspipe.sh %s
LEX=flex
LOCAL_MACHINE=octarine
LOGNAME=franky
[...]
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `4-global_variables`.
<hr>
</details>

<details>
	<summary>
		<b>Task 5. Local variables</b>
	</summary>
	<br>

Create a script that lists all local variables and environment variables, and functions.
```
julien@ubuntu:/tmp/0x03$ . ./5-local_variables
BASH=/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:histappend:interactive_comments:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=()
BASH_ARGV=()
BASH_CMDS=()
BASH_COMPLETION_COMPAT_DIR=/etc/bash_completion.d
BASH_LINENO=()
BASH_REMATCH=()
BASH_SOURCE=()
BASH_VERSINFO=([0]="4" [1]="3" [2]="46" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
BASH_VERSION='4.3.46(1)-release'
CLUTTER_IM_MODULE=xim
COLUMNS=133
COMPIZ_CONFIG_PROFILE=ubuntu
COMP_WORDBREAKS=$' \t\n"\'><=;|&(:'
DBUS_SESSION_BUS_ADDRESS=unix:abstract=/tmp/dbus-Fg27Lr20bq
DEFAULTS_PATH=/usr/share/gconf/ubuntu.default.path
DESKTOP_SESSION=ubuntu
[...]
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `5-local_variables`.
<hr>
</details>

<details>
	<summary>
		<b>Task 6. Local variable</b>
	</summary>
	<br>

Create a script that creates a new local variable.
- Name: `BEST`.
- Value: `School`.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `6-create_local_variable`.
<hr>
</details>

<details>
	<summary>
		<b>Task 7. Global variable</b>
	</summary>
	<br>

Create a script that creates a new global variable.
- Name: `BEST`.
- Value: `School`.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `7-create_global_variable`.
<hr>
</details>

<details>
	<summary>
		<b>Task 8. Every addition to true knowledge is an addition to human power</b>
	</summary>
	<br>

Write a script that prints the result of the addition of 128 with the value stored in the environment variable `TRUEKNOWLEDGE`, followed by a new line.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `8-true_knowledge`.
<hr>
</details>

<details>
	<summary>
		<b>Task 9. Divide and rule</b>
	</summary>
	<br>

Write a script that prints the result of `POWER` divided by `DIVIDE`, followed by a new line.
- `POWER` and `DIVIDE` are environment variables.
```
julien@production-503e7013:~$ export POWER=42784
julien@production-503e7013:~$ export DIVIDE=32
julien@production-503e7013:~$ ./9-divide_and_rule | cat -e
1337$
julien@production-503e7013:~$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `9-divide_and_rule`.
<hr>
</details>

<details>
	<summary>
		<b>Task 10. Love is anterior to life, posterior to death, initial of creation, and the exponent of breath</b>
	</summary>
	<br>

Write a script that displays the result of `BREATH` to the power `LOVE`
- `BREATH` and `LOVE` are environment variables.
- The script should display the result, followed by a new line.
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `10-love_exponent_breath`.
<hr>
</details>

<details>
	<summary>
		<b>Task 11. There are 10 types of people in the world -- Those who understand binary, and those who don't</b>
	</summary>
	<br>

Write a script that converts a number from base 2 to base 10.
- The number in base 2 is stored in the environment variable `BINARY`.
- The script should display the number in base 10, followed by a new line.
```
julien@production-503e7013:~/$ export BINARY=10100111001
julien@production-503e7013:~/$ ./11-binary_to_decimal
1337
julien@production-503e7013:~/$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `11-binary_to_decimal`.
<hr>
</details>

<details>
	<summary>
		<b>12. Combination</b>
	</summary>
	<br>

Create a script that prints all possible combinations of two letters, except `oo`.
- Letters are lower cases, from `a` to `z`.
- One combination per line.
- The output should be alpha ordered, starting with `aa`.
- Do not print `oo`.
- Your script file should contain maximum 64 characters.
```
julien@ubuntu:/tmp/0x03$ echo $((26 ** 2 -1))
675
julien@ubuntu:/tmp/0x03$ ./12-combinations | wc -l
675
julien@ubuntu:/tmp/0x03$ 
julien@ubuntu:/tmp/0x03$ ./12-combinations | tail -303 | head -10
oi
oj
ok
ol
om
on
op
oq
or
os
julien@ubuntu:/tmp/0x03$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `12-combinations`.
<hr>
</details>

<details>
	<summary>
		<b>13. Floats</b>
	</summary>
	<br>

Write a script that prints a number with two decimal places, followed by a new line.
- The number will be stored in the environment variable `NUM`.
```
betty  main.py
pandolowitz@JARVIS:~$ rm __pycache__/
rm: cannot remove '__pycache__/': Is a directory
pandolowitz@JARVIS:~$ rm -r __pycache__/
pandolowitz@JARVIS:~$ mkdir holberton_school
pandolowitz@JARVIS:~$ 
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `13-print_float`.
<hr>
</details>

<details>
	<summary>
		<b>14. Decimal to Hexadecimal</b>
	</summary>
	<br>

Write a script that converts a number from base 10 to base 16.
- The number in base 10 is stored in the environment variable `DECIMAL`.
- The script should display the number in base 16, followed by a new line.
```
julien@production-503e7013:~/$ export DECIMAL=16
julien@production-503e7013:~/$ ./14-decimal_to_hexadecimal
10
julien@production-503e7013:~/$ export DECIMAL=1337
julien@production-503e7013:~/$ ./14-decimal_to_hexadecimal | cat -e
539$
julien@production-503e7013:~/$ export DECIMAL=15
julien@production-503e7013:~/$ ./14-decimal_to_hexadecimal | cat -e
f$
julien@production-503e7013:~/$
```
#
**Repo:**
- GitHub repository: `holbertonschool-shell`.
- Directory: `init_files_variables_and_expansions`.
- File: `14-decimal_to_hexadecimal`.
<hr>
</details>

## 📂 Files description

| **FILE** | **DESCRIPTION** |
| :-----: | ----- |
| 0-alias | Script to create an alias named `ls` with the value `rm *`. |
| 1-hello_you | Script to print `hello user`, where `user` is the current Linux user. |
| 2-path | Script to add `/action` to the `PATH` environment variable. |
| 3-paths | Script to count the number of directories in the `PATH` environment variable. |
| 4-global_variables | Script to list environment variables. |
| 5-local_variables | Script to list all local variables, environment variables, and functions. |
| 6-create_local_variables | Script to create a new local variable named `BEST` with the value `School`. |
| 7-create_global_variable | Script to create a new global variable named `BEST` with the value `School`. |
| 8-true_knowledge | Script to print the result of adding 128 to the value stored in the `TRUEKNOWLEDGE` environment variable. |
| 9-divide_and_rule | Script to print the result of dividing the value of `POWER` by `DIVIDE`, where both are environment variables. |
| 10-love-exponent_breath | Script to display the result of raising the value of `BREATH` to the power of `LOVE`, both being environment variables. |
| 11-binary_to_decfimal | Script to convert a binary number stored in the `BINARY` environment variable to decimal and print the result. |
| 12-combinatons | Script to print all possible combinations of two lowercase letters except `oo`. |
| 13-print_float | Script to print a number with two decimal places from the `NUM` environment variable. |
| 14-decimal_to_hexadecimal | Script to convert a decimal number stored in the `DECIMAL` environment variable to hexadecimal and print the result. |

## ♥️ Thanks

A big thank you to all my Holberton School peers for their help and support throughout these projects.