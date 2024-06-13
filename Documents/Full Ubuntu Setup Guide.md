# Full Setup Guide for Linux Ubuntu

**1.**  Login to Ubuntu Terminal and make sure you are on your home folder as default.

**2.**  Use ```wget``` command to download the below files in your home drive, as define in table.


| File Name | URL with Wget |
| --- | --- |
| 01_KeyCreation | $ wget "https://raw.githubusercontent.com/hpngithub/GitHubKB/main/SSH%20Public%20Key/Linux%20ubuntu/01_KeyCreation"
| 02_InstallGit&Keychain | $ wget https://raw.githubusercontent.com/hpngithub/GitHubKB/main/SSH%20Public%20Key/Linux%20ubuntu/02_InstallGit%26Keychain|
| 03_ConfigGit | $ wget "https://raw.githubusercontent.com/hpngithub/GitHubKB/main/SSH%20Public%20Key/Linux%20ubuntu/03_ConfigGit" |

**3.** Next open the ```01_KeyCreation``` file using below command:

     $ nano ~/01_KeyCreaton

**4.** Replace only the ``` < YOURUSERNAME > ``` to your localhost username, then save **CTRL+O** and close **CTRL+X**.

**5.** Next use below command to make sure you give excutive access permission.

    $ chmod 775 01_KeyCreation 02_InstallGit&Keychain 03_ConfigGit

**6.** Next run the below command to setup and obtain public key.

    $ 


Follow the [03.Repository SSH URL Guide](https://github.com/hpngithub/GitHubKB/blob/main/Documents/03.Repository%20SSH%20Url%20Guide.md) to obtain the url of your repository.

* **"03.Repository SSH URL Guide URL" =** "https://github.com/hpngithub/GitHubKB/blob/main/Documents/03.Repository%20SSH%20Url%20Guide.md"

 