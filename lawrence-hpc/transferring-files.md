# Transferring Files

Transferring files onto and off of your Lawrence home directory can be done using several methods available to researchers at USD. This section will cover the movement of files between local systems and the Lawrence HPC.

{% hint style="info" %}
Note: For **very large files**, please see the CyberDuck section below, and use a desktop or computer with a wired internet connection \(not wifi\) if possible.
{% endhint %}

## Drag-and-Drop Option

If you prefer to move files using the drag-and-drop method, it is possible using MobaXterm or Cyberduck. This file moving method uses sftp, or SSH \(or Secure\) File Transfer Protocol. For this we will open up MobaXterm or Cyberduck.

{% hint style="info" %}
For help downloading MobaXterm, click [here](https://usdrcg.gitbook.io/docs/~/edit/drafts/-LUGvCyCLVx1LFQp3u6h/software-and-apps/lumerical-fdtd-on-lawrence-gui#install-mobaxterm).
{% endhint %}

### **MobaXterm**

In MobaXterm, the file explorer/hierarchy is visible just to the left of the command line interface.

![](../.gitbook/assets/screenshot-10%20%282%29.png)

From this section of the MobaXterm window, you can drag and drop files between either computer as you desire.

![](../.gitbook/assets/mobaxmovingfile.png)

![](../.gitbook/assets/screenshot-8.png)

### **Cyberduck**

Cyberduck can also be used for moving files by sftp in Windows and Mac, but not Linux. You can find the Cyberduck installation [here](https://cyberduck.io/). Once installed, opening Cyberduck should return a window as follows:

![](../.gitbook/assets/image%20%2853%29.png)

You will need to open a connection by clicking on the 'Open Connection' icon. This will return a window to fill in with the host information. Fill this window in as shown below \(note user.name will be your personal Lawrence username\). Be sure to choose SFTP and port 22:

![](../.gitbook/assets/cyberduck_2.bin)

After successfully connecting, you can upload files into your Lawrence folders on your home directory by dragging and dropping from your desktop... 

![](../.gitbook/assets/cyberduckmovefile.png)

or by clicking the upload icon at the top of the Cyberduck display.

![](../.gitbook/assets/screenshot-19.png)

![](../.gitbook/assets/screenshot-21.png)

## Command Line SCP

The standard command line method for file movement between hosts is the `scp`command \(secure copy\). This is an ssh based protocol designed for moving files between local and remote hosts. To get files from your local computer, you will need to open a local terminal session on your computer \(Do not connect to the HPC! In this example, local@xyz is my local PC\).

```text
[local@xyz ~]$
```

The syntax of the `scp` command has three parts: 

1. scp command
2. current path to file to be moved
3. target path where the file will be sent

Type the `scp` command as follows \(type the path you want your file transferred to on Lawrence; here I use ''some.folder'\):

```text
[local@xyz ~]$ scp  ./pathTo/file/file.name User.Name@Lawrence.usd.edu:/home/usd.local/user.name/some.folder
user.name@lawrence.usd.edu's password: 
file.name              100% 8893     8.7KB/s   00:00
```

Hints:

* If you are logging into Lawrence as a user from another school \(not USD\), "usd.local" may be replaced by an identifier for your school: \(e.g. user.name@lawrence.usd.edu:/home/**blackhills.local**/user.name/some.folder\)
* Don't forget either the period \(.\) at the start of the initial path to the file \(it refers to the current working directory \(the directory you are located in\)\) or a complete path to the file \(/home/Desktop/pathTo/file/file.name\)
* Don't forget the colon \(:\) after ".edu"
* To transfer directories, add an -r flag

```text
[user.name@login@login some.folder]$ scp -r ./pathTo/and/including/myDirectory/ User.Name@Lawrence.usd.edu:/home/usd.local/user.name/
contents.c                                      100%  1KB    45KB/s    00:00
of.c                                            100%  2KB    44KB/s    00:00
directory.c                                     100%  2KB    43KB/s    00:00
```

Open a second terminal and log in to Lawrence, then list directories.  The file file.name has been transferred.

```text
[user.name@login@login some.folder]$ ls
file.name
```

The last line in the first terminal gives stats on the transfer.  In a second terminal, where you are logged into Lawrence, you can check that the file was transferred and put into some.folder.

You can also use scp for other data transfer applications including HPC to local PC, between HPCs, and between PCs. To transfer files from Lawrence to your PC, \(while not logged in to Lawrence\) simply switch the two paths in the scp command \(numbers 2 and 3\), and move the filename to the end of the first path.  If needed, change "usd.local" to the reference for your institution.

```text
[local@xyz ~]$ scp User.Name@Lawrence.usd.edu:/home/usd.local/user.name/some.folder/file.name  ./pathTo/file/
user.name@lawrence.usd.edu's password: 
file.name              100% 8893     8.7KB/s   00:00
```

