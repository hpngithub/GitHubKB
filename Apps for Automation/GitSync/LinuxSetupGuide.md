# Git-Sync Linux Setup Guide

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
    ```branch.master.sync true```

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
    
>    **A.** At this time you should be still in the ```Git-Sync``` directory. In there to create the ```AutoSync-Repos.sh``` , use below command:

>    $ nano Autosync-Repos.sh

> 


**08.** Create the ```AutoGitSyncRepo.service``` service file.


**09.** Create the ```AutoGitSyncRepo.timer``` service file.


**10.** Enable and Start the ```AutoGitSyncRepo.service``` and  ```AutoGitSyncRepo.timer``` services to auto run the ```git-sync``` to sync the Github repository with local repository.

</BR>
</BR>

#### SOURCES
+ Git-Sync Main : https://github.com/simonthum/git-sync
+ Main Guide : https://www.worthe-it.co.za/blog/2016-08-13-automated-syncing-with-git.html
+Nice Program Understanding : https://en.wikipedia.org/wiki/Nice_(Unix)
+ Added SSH Agent in script : https://serverfault.com/questions/547923/running-ssh-agent-from-a-shell-script
+ Enable Service & Timer Command : https://askubuntu.com/questions/1083537/how-do-i-properly-install-a-systemd-timer-and-service
+ Ubuntu Systemd Service :  https://manpages.ubuntu.com/manpages/bionic/man5/systemd.service.5.html
+ Ubuntu Systemd Unit : https://manpages.ubuntu.com/manpages/bionic/man5/systemd.unit.5.html
+ Ubuntu Systemd timer : https://manpages.ubuntu.com/manpages/bionic/man5/systemd.timer.5.html
+ Systemd Log File : https://stackoverflow.com/questions/37585758/how-to-redirect-output-of-systemd-service-to-a-file + https://www.baeldung.com/linux/redirect-systemd-output-to-file
