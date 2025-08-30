# Git-Sync Linux Setup Guide
### Note: This guide work on Ubuntu, Debian & Fedora

+ :exclamation: ** Prequesite : **

    + *_Must have full path of clone repository exist in localmachine. As created during [Linux Ubuntu Repository Cloning Guide](https://github.com/hpngithub/GitHubKB/blob/main/Documents/Linux%20Ubuntu%20Repository%20Cloning%20Guide.md)_*
    + *_Must keep the full path of Git-Sync folder, in order to setup and see service log file for future._*
    

## INSTRUCTION
**01.** Open the Ubuntu Terminal.

**02.** Go the clone repository folder as per [Linux Ubuntu Repository Cloning Guide](https://github.com/hpngithub/GitHubKB/blob/main/Documents/Linux%20Ubuntu%20Repository%20Cloning%20Guide.md).
    
> ${\color{green} My Repo : PythonBCProject}$
<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/01.png?raw=true" width="500x"/>

**03.** At this time you have 2 options, as shown below:

* **OPTION-A.SKIP :** If you followed [Linux Ubuntu Full Setup Guide : Section-C, Step-6] (https://github.com/hpngithub/GitHubKB/blob/main/Documents/Linux%20Ubuntu%20Full%20Setup%20Guide.md) 
    + **NOTE : If you like to verify below bloon flag is setup correctly, then can navigate to ```config``` file under **your clone repository folder/.git/** folder and use the command to verify.
    +     $ cat config
    +    ```branch.master.sync true``` 
    ```branch.master.syncNewFiles true```
    ```branch.main.sync true``` 
    ```branch.main.syncNewFiles true```

</br>
    
* **OPTION-B.SETUP BOOL FLAG :** In your home directory, initial below command one after another, as show in below image:

    ```$ git config --bool branch.master.sync true```

    ```$ git config --bool branch.master.syncNewFiles true```

    ```$ git config --bool branch.main.sync true```

    ```$ git config --bool branch.main.syncNewFiles true```

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/02.png?raw=true" width="500x"/>


</br>

     
**04.** Next create folder name ```Git-Sync``` and navigate in to the folder, using below command:

    $ mkdir Git-Sync
    $ cd Git-Sync

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/03.png?raw=true" width="500x"/>

**05.** After that in ```Git-Sync`` folder download ```git-sync``` script from github directory, by using below command:

    $ wget https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps/GitSync/git-sync

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/04.png?raw=true" width="500x"/>

**06.** Now give ```git-sync``` script as executable permission with below command:

    $ chmod -x git-sync

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/05.png?raw=true" width="500x"/>

**07.** Create the ```AutoSync-Repos.sh``` file and give the excutable permission.
    
+ **A.** At this time you should be still in the ```Git-Sync``` directory. In there to create the ```AutoSync-Repos.sh``` , use below command:

    $ nano Autosync-Repos.sh

+ **B.** Update the below text box information with correct path and past in the ```AutoSync-Repos.sh``` file.

    ``` 
    #!/bin/sh

    #Repo 1
    cd <REPO FULL PATH>
    eval `ssh-agent`
    ssh-add <Key FULL PATH> 
    bash <Git-Sync FULL PATH>
    eval `ssh-agent -k`

    #Repo 2
    cd <REPO FULL PATH>
    eval `ssh-agent`
    ssh-add <Key FULL PATH>
    bash <Git-Sync FULL PATH>
    eval `ssh-agent -k`

    ```

    *_Note You can add as much github repository as you desire. As for my case is only 1 repository, as per image below :_*

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/06.png?raw=true" width="500x"/>

    *_`cd <REPO FULL PATH>` It is full path to your clone repository_*

    *_`ssh-add <Key FULL PATH>` Normally in linux, it is /home/yourusername/.ssh/yourkeyname_*

+ **C.** Next press keyboard shortcut, CTRL+O & CTRL+X to save and Exit.

+ **D.** Now give ```AutoSync-Repos.sh``` script as executable permission with below command:

    $ chmod -x AutoSync-Repos.sh 

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/07.png?raw=true" width="500x"/>

    
**08.** Create the ```AutoGitSyncRepo.service``` service file.

<mark>**Note :** Before creating the "Autosync-Repos.sh" file on Fedora Linux, update the permission for private key "Github" using below command:</mark>

<mark>$ chmod 644 /home/SysAdmin/.ssh/Github</mark>

<mark><img src="https://github.com/hpngithub/GitHubKB/blob/main/Apps%20for%20Automation/GitSync/Images/08.Fedora.png?raw=true" Width="500x"/></mark>


+ **A.** Use below command to create the ```AutoGitSyncRepo.service``` service file

    $ nano AutoGitSyncRepo.service

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/08.png?raw=true" width="500x"/>

+ **B.** Update the below text box information with correct path and past in the ```AutoGitSyncRepo.service``` file.

    ```
    [Unit]
    Description=Automatically push and pull on repos
    
    [Service]
    Type=simple
    ExecStart=/bin/sh <FULL PATH WITH of Autosync-Repos.sh FILE>
    Nice=19
    StandardOutput=append:<FULL PATH OF LOCATION WITH DESIRE NAME OF .log FILE>
    StandardError=append:<FULL PATH OF LOCATION WITH DESIRE NAME OF .log FILE, IT CAN BE SAME>
    
    [Install]
    WantedBy=AutoGitSyncRepo.target
    
    ```

    *_ExecStart=/bin/sh `<FULL PATH OF Autosync-Repos.sh FILE>` It is full path to location of Autosync-Repos.sh file_*

    *_StandardOutput=append:`<FULL PATH OF .log FILE>` It is your desire path where do you like have log file created._*

    *_StandardError=append:`<FULL PATH OF .log FILE, IT CAN BE SAME as Above>` It is your desire path where do you like have log file created._*

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/09.png?raw=true" width="500x"/>

+ **C.** Next press keyboard shortcut, CTRL+O & CTRL+X to save and Exit.

**09.** Create the ```AutoGitSyncRepo.timer``` service file.

+ **A.** Use below command to create the ```AutoGitSyncRepo.timer``` service file

    $ nano AutoGitSyncRepo.timer

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/10.png?raw=true" width="500x"/>

+ **B.** copy and past below text in the ```AutoGitSyncRepo.timer``` file.

    ```
    [Unit]
    Description=Automatically push and pull on repos
    
    [Timer]
    OnBootSec=1min
    OnUnitActiveSec=5min
    
    [Install]
    WantedBy=timers.target
    
    ```

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/11.png?raw=true" width="500x"/>

+ **C.** Next press keyboard shortcut, CTRL+O & CTRL+X to save and Exit.

**10.** Enable and Start the ```AutoGitSyncRepo.service``` and  ```AutoGitSyncRepo.timer``` services in order to run the ```git-sync``` **(Every 5min)** to sync the Github repository with local repository, use all `systemctl_` below command using below commands:

<mark>**Note :** !!ON FEDORA!! Before start the "Autosync-Repos" service and timer file, use below command to create symlink and reload-daemon in systemd.</mark>

<mark>$ systemctl link --user /Github/Git-sync/AutoGitSyncRepo.service</mark>

<mark>$ systemctl link --user /Github/Git-sync/AutoGitSyncRepo.timer</mark>

<mark>$ systemctl --user daemon-reload</mark>

<mark><img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/12.Fedora.png?raw=true" width="500x"/></mark>

<mark> **SKIP BELOW COMMAND ON FEDORA** </mark>

    $ systemctl --user enable <FULL PATH to AutoGitSyncRepo.service> 
</BR>

**_Note: `<FULL PATH to AutoGitSyncRepo.service>` replace with full path of the location of AutoGitSyncRepo.service as indicated in above step 08._**

<mark> **SKIP BELOW COMMAND ON FEDORA** </mark>
        
    $ systemctl --user enable <FULL PATH to AutoGitSyncRepo.timer>
</BR>

**_Note: `<FULL PATH to AutoGitSyncRepo.timer>` replace with full path of the location of AutoGitSyncRepo.timer as indicated in above step 09._**

    $ systemctl --user start AutoGitSyncRepo.service
</BR>

    $ systemctl --user start AutoGitSyncRepo.timer
</BR>

    $ systemctl --user enable AutoGitSyncRepo.service
</BR>

    $ systemctl --user enable AutoGitSyncRepo.timer
</BR>

    $ systemctl --user status AutoGitSyncRepo.service
</BR>

    $ systemctl --user status AutoGitSyncRepo.timer

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/12.png?raw=true" width="500x"/>

<mark> **Note: My full path to services  and timer is listed in image below: (FEDORA)** </mark>

<img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/13.Fedora.png?raw=true" width="500x"/>


</BR>
</BR>

--- 

##### SOURCES
+ ##### *_Git-Sync Main : https://github.com/simonthum/git-sync_*
+ ##### *_Main Guide : https://www.worthe-it.co.za/blog/2016-08-13-automated-syncing-with-git.html_*
+ ##### *_Nice Program Understanding : https://en.wikipedia.org/wiki/Nice_(Unix)_*
+ ##### *_Added SSH Agent in script : https://serverfault.com/questions/547923/running-ssh-agent-from-a-shell-script_*
+ ##### *_Enable Service & Timer Command : https://askubuntu.com/questions/1083537/how-do-i-properly-install-a-systemd-timer-and-service_*
+ ##### *_Ubuntu Systemd Service :  https://manpages.ubuntu.com/manpages/bionic/man5/systemd.service.5.html_*
+ ##### *_Ubuntu Systemd Unit : https://manpages.ubuntu.com/manpages/bionic/man5/systemd.unit.5.html_*
+ ##### *_Ubuntu Systemd timer : https://manpages.ubuntu.com/manpages/bionic/man5/systemd.timer.5.html_*
+ ##### *_Systemd Log File : https://stackoverflow.com/questions/37585758/how-to-redirect-output-of-systemd-service-to-a-file + https://www.baeldung.com/linux/redirect-systemd-output-to-file_*
+ ##### *_FEDORA (SystemLink) : https://unix.stackexchange.com/questions/194175/can-i-use-a-symbolic-link-as-a-service-of-systemd + https://unix.stackexchange.com/questions/271541/enabling-linked-unit-files-in-systemd_*
+ ##### *_FEDORA (Start Service) : https://nts.strzibny.name/systemd-user-services/_*
