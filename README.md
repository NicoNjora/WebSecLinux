# Group 1 - Linux

## Installation
Download ubuntu desktop iso file from **https://ubuntu.com/download/desktop**

If on Windows:
    - Download Putty from **https://www.putty.org/**

Follow installation instructions.

## Basic Linux Commands

#### Finding your current directory
``` pwd ```

#### Go into another directory
``` cd <directory_name>```

#### Listing a folder's contents:
``` $ ls ```

#### Making a directory
``` mkdir <directory_name>```

#### Removing a directory
``` rmdir <directory_name>```

**Example Output**: 
Desktop
Downloads
Documents
file.txt

#### Checking what a command does
```man <command>​```
- Example: ```man ls```

#### SSH
``` ssh <host> -p <port> -l <login_name>```
- Example: ```ssh bandit0@bandit.labs.overthewire.org -p 2220```

For more commands check out this [tutorial](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners)

## OverTheWire games
- The wargames offered by the OverTheWire community can help you to learn and practice security concepts in the form of fun-filled games.

- [Bandit](#bandit)
- [Natas](#natas)

## Bandit 

#### Level 0:
The goal of this level is for you to log into the game using SSH. 
- host - **bandit.labs.overthewire.org​**
- port - ​**2220​**
- username - ​**bandit0​**
- password - ​**bandit0​**

Linux command:
**ssh bandit0@bandit.labs.overthewire.org -p 2220**

#### Level 0 → Level 1 :
The password for the next level is stored in a file called ​readme​ located in the ​home directory​. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game. 
 
Commands required for this level:
ls and cat. 
```$ ls```
- ​Output:​: readme
```$ cat readme**```
​- Output:​ boJ9jbbUNNfktd78OOpsqOltutMc3MY1

This returns first password of the game, i.e., **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**

#### Level 1 → Level 2:
The password for the next level is stored in a file called ‘ ​- ’​ located in the home directory

```$ ssh bandit1@bandit.labs.overthewire.org -p 2220 ```

**NOTE:**​ ​Before login to the next level you should exit the current level. To do this type ​exit ​in your terminal.  Then use the above command to login. Then enter the password you found in ​readme ​file in the previous step

```$ ​ls ```
- Output: ​ - 

The problem here is that ​cat​ is recognizing the dash ( - )as synonym for stdin. In order to fix this we need to specify the dash is a file using a dot and a forward slash as follows ‘cat ./-’

```$ cat ./- ```
- Output:​ CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9 

#### Level 2 → Level 3:
The password for the next level is stored in a file called ​**spaces in this filename**​ located in the home directory 

```$ ​ssh bandit2@bandit.labs.overthewire.org​ -p 2220 ```

Enter the password that you found out in the previous step.    

###### Then use the following commands: 
```$ ​ls  ```
- Output:​ spaces in this filename 

```$ ​cat spaces\ in\ this\ filename ```
- Output:​ UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK 

This returns the third password.

- **NOTE:** ​You do not have to type the whole word ‘spaces\ in\ this\ filename’ in the terminal. Enter the first few letters and click on tab button. The name will auto-complete itself. 
 
#### Level 3 → Level 4 
The password for the next level is stored in a hidden file in the ​inhere​ directory. 
```$ ​ssh​ bandit3@bandit.labs.overthewire.org -p 2220``` 
- Remember to exit the previous level before login to the current level. Then enter the password that you found out in the previous step.

```$ ​ls```
- Output:​ inhere 


```$ ​cd inhere```

``` $ ​ls -la ```

- Output:​ 

total 12 
drwxr-xr-x 2 root    root    4096 Oct 16  2018 . drwxr-xr-x 3 root    root    4096 Oct 16  2018 .. -rw-r----- 1 bandit4 bandit3   33 Oct 16  2018 .hidden```
 
```$ ​cat .hidden```
- Output:​ pIwrPrtPN36QITSp3EQaw936yaFoFgAB 

This returns the next password. 
 
#### Level 4 → Level 5
The password for the next level is stored in the only human-readable file in the ​inhere​ directory.
- **Tip**: if your terminal is messed up, try the “reset” command. 

```$ ​ssh bandit4@bandit.labs.overthewire.org​ -p 2220 ```

```$ ​ls```
- Output:​ inhere

```$ ​cd inhere ```


```$ ls -la ```
 
- **Output:**
total 48 
drwxr-xr-x 2 root    root    4096 Oct 16  2018 . drwxr-xr-x 3 root    root    4096 Oct 16  2018 .. -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file00 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file01 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file02 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file03 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file04 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file05 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file06 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file07 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file08 -rw-r----- 1 bandit5 bandit4   33 Oct 16  2018 -file09 

```$ ​cat ./-file07```
- Output:​ **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**

This returns the next password.

#### Level 5 → Level 6
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
human-readable
1033 bytes in size
not executable

$ ssh bandit5@bandit.labs.overthewire.org -p 2220
$ ls
Output: inhere
 
$ cd inhere
$ ls -la
Output:
 total 88
drwxr-x--- 22 root bandit5 4096 Oct 16  2018 .
drwxr-xr-x  3 root root    4096 Oct 16  2018 ..
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere00
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere01
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere02
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere03
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere04
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere05
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere06
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere07
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere08
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere09
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere10
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere11
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere12
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere13
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere14
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere15
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere16
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere17
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere18
drwxr-x---  2 root bandit5 4096 Oct 16  2018 maybehere19

$ find . -type f -readable ! -executable -size 1033c
Output: ./maybehere07/.file2
$ cat ./maybehere07/.file2
Output: DXjZPULLxYr17uwoI01bNLQbtFemEgo7


#### Level 6 → Level 7

The password for the next level is stored somewhere on the server and has all of the following properties:
owned by user bandit7
owned by group bandit6
33 bytes in size

$ ssh bandit6@bandit.labs.overthewire.org -p 2220

$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
Output:/var/lib/dpkg/info/bandit7.password

$ cat /var/lib/dpkg/info/bandit7.password

Output: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

#### Level 7 → Level 8
The password for the next level is stored in the file data.txt next to the word millionth

$ ssh bandit7@bandit.labs.overthewire.org -p 2220
$ ls
Output: data.txt
 
$ cat data.txt | grep "millionth"
Output: millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV

#### Level 8 → Level 9
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

$ ssh bandit8@bandit.labs.overthewire.org -p 2220
$ ls
Output: data.txt
$ cat data.txt | sort | uniq -u

Output: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

#### Level 9 → Level 10
The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.

$ ssh bandit9@bandit.labs.overthewire.org -p 2220
$ ls
Output: data.txt
$ strings data.txt | grep "="
Output:
2========== the
========== password
>t=	yP
rV~dHm=
========== isa
=FQ?P\U
=	F[
pb=x
J;m=
=)$=
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
iv8!=

For more information and information about the other levels follow the below links and continue playing and learning.
https://medium.com/@Kan1shka9/overthewire-wargames-bandit-walkthrough-df2b86826c67

http://overthewire.org/wargames/bandit/bandit6.html
http://linuxcommand.org/



###  Natas

#### Level 0:
- Username: natas0
- Password: natas0 
- URL:​http://natas0.natas.labs.overthewire.org 

#### Level 0 -> Level 1:

Level 0 solution to get Level 1 password: Right click on the web page and view page source. 
- PASSWORD for natas1 **IS:gtVrDuiDfck831PqWsLEZy5gyDz1clto** on the commented section.

#### Level 1 -> Level 2:

Use **Ctrl + U** to display non-editable HTML source code for the current page particularly if the right click functionality is  blocked and obtain the password in the commented section. 

- You can also go to the console section, and you will be able to view the HTML code

#### Level 2 -> Level 3:
