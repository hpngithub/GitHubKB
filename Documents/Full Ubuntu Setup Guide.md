# Full Setup Guide for Linux Ubuntu

*_**Note :**  This guide is only for Linux Ubuntu v22.04 or higher._*

<br>

## A. DOWNLOAD SCRIPT
**01.**  Login to Ubuntu Terminal and make sure you are on your home folder as default.

**02.**  Use ```wget``` command to download the below files in your home drive, as define in table.


| File Name | URL with Wget |
| --- | --- |
| 01_KeyCreation | $ wget "https://raw.githubusercontent.com/hpngithub/GitHubKB/main/SSH%20Public%20Key/Linux%20ubuntu/01_KeyCreation"
| 02_InstallGit&Keychain | $ wget https://raw.githubusercontent.com/hpngithub/GitHubKB/main/SSH%20Public%20Key/Linux%20ubuntu/02_InstallGit%26Keychain|
| 03_ConfigGit | $ wget "https://raw.githubusercontent.com/hpngithub/GitHubKB/main/SSH%20Public%20Key/Linux%20ubuntu/03_ConfigGit" |

<br>

## B. ADDING USER-NAME TO ```01_KeyCreation``` FILE
**03.** Next open the ```01_KeyCreation``` file using below command:

     $ nano ~/01_KeyCreaton

**4.** Replace only the ``` < YOURUSERNAME > ``` to your localhost username, then save **CTRL+O** and close **CTRL+X**.

<br>

## C. ADDING USER-NAME TO ```01_KeyCreation``` & EXCUTING ALL 3 FILES
**05.** Next use below command to make sure you give excutive access permission.

    $ chmod 775 01_KeyCreation 02_InstallGit&Keychain 03_ConfigGit


**06.** Next run the below command to initiate script to obtain keys.

    $ sh 01_KeyCreation

**07.** You should see the 2 keys listed is ```private key``` and one is ```public key```, as shown on below

> **Example :** ```Github``` *No ".pub" = private key, **!!DO NOT SHOW OR SHARE TO 3rd-Party!!*** 
> **Example :** ```Github.pub``` *Yes ".pub" = public key to use on Github* 

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Documents/Images/Exsshkey.png?raw=true" width="500x"/>

**08.** Now copy **Public Key** starting ```ssh-rsa`` to end of paragraph and login to github.com

<br>

## D. LOCALHOST KEY TO GITHUB.COM TO ACCESS REPOSITORY
**09.** Follow [01.Add SSH Public Key Guide](https://github.com/hpngithub/GitHubKB/blob/main/Documents/01.Add%20SSH%20Public%20Key%20Guide.md) to add key to Github.

* **"01.Add SSH Public Key Guide URL" =** "https://github.com/hpngithub/GitHubKB/blob/main/Documents/01.Add%20SSH%20Public%20Key%20Guide.md"

<br>

## E. CREATE NEW EMPTY REPOSITORY & GET REPOSITORY URL FOR COLONING
**10.** Follow [02.Create Repository Guide](https://github.com/hpngithub/GitHubKB/blob/main/Documents/02.Create%20Repository.md) to create repository

* **"02.Create Repository Guide URL" =** "https://github.com/hpngithub/GitHubKB/blob/main/Documents/02.Create%20Repository.md"

**11.** Follow [03.Repository SSH URl Guide](https://github.com/hpngithub/GitHubKB/blob/main/Documents/03.Repository%20SSH%20Url%20Guide.md)

* **"03.Repository SSH Url Guide URL" =** "https://github.com/hpngithub/GitHubKB/blob/main/Documents/03.Repository%20SSH%20Url%20Guide.md"

<br>

## F. CLONE THE REPOSITORY
**12.** To clone repository on the terminal, use below command:

    $ git clone [YOUR REPOSITORY URL]
    
**_*My URL : git@github.com:hpngithub/PythonBCProject.git*_**

**_*My Command : git clone git@github.com:hpngithub/PythonBCProject.git, as shown below image.*_**

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Documents/Images/gitclonecmd.png?raw=true" width="500x"/>

**13.** To view and check if clone of repository successfull, use below command:

    $ cd <YOUR REPOSITORY NAME>
    $ ls -all
    $ git status

**_*My Repository name is ```PythonBCProject```, as you can see in My url repo path on step 12 above and in below image.*_**

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Documents/Images/RepoClonecheck.png?raw=true" width="500x"/>

<br>

## G. SETUP ```Git-Sync``TO AUTOMATE GITHUB = LOCALHOST
**14.** Follow [NAME](URL) to automate Github sync with localhost by using ```git-sync``` file.

* **"NAME" =** "URL"









 