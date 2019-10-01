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
```` mkdir <directory_name>```

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

### Bandit 

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
 
**Level 4 → Level 5**
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
