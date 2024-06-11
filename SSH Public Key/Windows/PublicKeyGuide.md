# Generating Public Key Guide For Windows 10 & 11

1. Press the Windows key or open up the Start Menu. Type “cmd”.
2. Under “Best Match”, click “Command Prompt”.
3. In the command prompt, use the ssh-keygen command:
<img src="https://github.com/hpngithub/GitHubKB/blob/main/SSH%20Public%20Key/Windows/Images/S3.png?raw=true" width="400x"/>

5. Press enter for default file save (~/.ssh/id_rsa)
<img src="https://github.com/hpngithub/GitHubKB/blob/main/SSH%20Public%20Key/Windows/Images/S4.png" width="400x"/>
By default, the system will save the keys to [your home directory]/.ssh/id_rsa.  Unless you are an expert you should use the default option and press Enter.

6. Press enter for default passphrase (no passphrase)
<img src="https://github.com/hpngithub/GitHubKB/blob/main/SSH%20Public%20Key/Windows/Images/S5.png" width="400x"/>

7. The system will now generate the key pair and display the key fingerprint and a randomart image. These fingerprints are not needed in day-to-day use of your keys but can be saved to your notes to identify your keys later if needed.
<img src="https://github.com/hpngithub/GitHubKB/blob/main/SSH%20Public%20Key/Windows/Images/S6.png" width="400x"/>

8. Open your file explorer.  You can now navigate to the hidden “.ssh” directory in your home folder. You should see two new files. The identification is saved in the id_rsa file and the public key is labeled id_rsa.pub. This is your SSH key pair. They are both saved in plain text.
<img src="https://github.com/hpngithub/GitHubKB/blob/main/SSH%20Public%20Key/Windows/Images/S7.png" width="400x"/>

9. Next to use your new keys with .pub to view and copy the key to git hub using ["Add SSH Public Key Guide"](https://github.com/hpngithub/GitHubKB/blob/main/Documents/Add%20SSH%20Public%20Key%20Guide.md/ "Visit Add SSH Public Key Guide!").

####  SOURCES :

* https://www.howtogeek.com/762863/how-to-generate-ssh-keys-in-windows-10-and-windows-11/
* https://stackoverflow.com/questions/31813080/generate-new-ssh-keys-in-windows-10-11
* https://www.purdue.edu/science/scienceit/ssh-keys-windows.html 
