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
    + **NOTE : If you like to verify below bloon flag is setup correctly, then can navigate to ```config``` file under "your clone repository folder/.git/" folder and use the ```cat config``` command to verify. 

        ```$ git config --bool branch.master.sync true```
    
        ```$ git config --bool branch.master.syncNewFiles true```
    
        ```$ git config --bool branch.main.sync true```
    
        ```$ git config --bool branch.main.syncNewFiles true```
    
* **OPTION-B.SETUP BOOL FLAG :** In your home directory, initial below command one after another, as show in below image:

    ```$ git config --bool branch.master.sync true```

    ```$ git config --bool branch.master.syncNewFiles true```

    ```$ git config --bool branch.main.sync true```

    ```$ git config --bool branch.main.syncNewFiles true```

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/02.png?raw=true" width="500x"/>

**04.** Next create folder name ```Git-Sync``` and navigate in to the folder, using below command:

    $ mkdir Git-Sync
    $ cd Git-Sync

    <img src="https://raw.githubusercontent.com/hpngithub/GitHubKB/main/Apps%20for%20Automation/GitSync/Images/03.png?raw=true" width="500x"/>

**05.** Next give the excuitexecutable permission to ```Git-Sync``` folder, by using below command:

    $