# Login

{% hint style="warning" %}
**Permission** from the HPC administrator is needed to access Lawrence.  Please email the ServiceDesk \(servicedesk@usd.edu\) to request an account, and **CC** the Research Computing Group \(rcg@usd.edu\).
{% endhint %}

{% hint style="info" %}
* **USD users:** Lawrence login information will be based on your USD login \(e.g. your password will be the same as for your email account\)
* **Non-USD users**: receive an email from the ServiceDesk regarding login information and/or password creation after the account is set up.  

For assistance or to ask questions, please contact the ServiceDesk \(servicedesk@usd.edu\).  Make sure to include the job id of your initial account request.
{% endhint %}

![](../.gitbook/assets/lawrencediagram2%20%281%29.png)

The Lawrence Supercomputer: Lawrence is composed of a many nodes. The user logs into the login node from their computer. From there they can access many other nodes in order to run analyses. The GPU node is used for graphics processing, and computations involving matrices. The high-memory \(himem\) node contains increased RAM for jobs that require high memory. The VIZ node is used for making visualizations. Besides the special purpose nodes, Lawrence contains 80 computational nodes for data analysis.  The data storage nodes act like a harddrive, albeit much faster, storing the files that are on the user's \(or lab's\) account.  Caution: the storage nodes are not backed up-be sure to back up your files.  The management node is utilized for managing the system.

## Lawrence SSH Login for Mac

### Install XQuartz

{% hint style="warning" %}
If using a **USD issued computer**, you may need **administrative permissions**.  Please contact the ServiceDesk for assistance if these permissions prevent installation of the software.  Make sure to include details like the software name.

**Example:**  "I have recently been provisioned an account on Lawrence, and I am following the tutorial instructions found at the RCG docs site \([https://usdrcg.gitbook.io/docs/lawrence-hpc/login\#lawrence-ssh-login-for-mac](https://usdrcg.gitbook.io/docs/lawrence-hpc/login#lawrence-ssh-login-for-mac)\) to download XQuartz.  My computer is USD issued, and requires administrative permissions to install the software.  Because I don't have this level of access, I would like help in installing this software."
{% endhint %}

To begin, first download the XQuartz installer [here](https://www.xquartz.org/).

![](../.gitbook/assets/1.download.png)

Go to your downloads and open the installer.

![](../.gitbook/assets/2.5.png)

Run the installer. \(If using a USD computer, an administrative username/password may be needed for this step.\)

![](../.gitbook/assets/3.4.png)

### Log into Lawrence

Search for the terminal in the Finder window

![](../.gitbook/assets/4.1.png)

It will start with a command prompt \(a line that ends with "$"\).

![](../.gitbook/assets/5.1a.png)

Next, login to Lawrence via an ssh session through the login node.  The output you see will be different depending on how your Duo account is setup.  First is if your account uses 'Push Notification' for your Duo secondary authentication.

```text
ITSCkMac07:~ user.name$ ssh User.Name@lawrence.usd.edu
Keyboard-interactive authentication prompts from server:
| Password:
| Duo two-factor login for user.name@usd.edu
|
| Enter a passcode or select one of the following options:
|
|  1. Duo Push to XXX-XXX-####
|
| Passcode or option (1-1): 1
| Success. Logging you in...
End of keyboard-interactive prompts from server
```

If you use a Token, your login will look more like this

```text
ITSCkMac07:~ user.name$ ssh User.Name@lawrence.usd.edu
Password: 
Duo two-factor login for user.name@usd.edu

Enter a passcode or select one of the following options:

Passcode: ######
```

{% hint style="info" %}
Note: your **password** will **not show up** as you type and it may look like nothing is happening.  It may seem strange, but keep typing, the remote system is still picking up your keystrokes and when you hit enter your password will be checked. However, the **passcode** you type in from your Duo token **will show up** as you type, this is normal.
{% endhint %}

If it accepts the password and your second Duo authentication method, it will show a welcome message and a prompt \(a line that ends with '$'\).

```text
Last login: (date and address here)
### Other information.... ###
###                       ###
###                       ###
[user.name@usd.local@login ~]$ 
```

{% hint style="info" %}
If **libgl errors** appear when running a GUI \(e.g. rstudio\), then before running the software, try exporting this environmental variable:

```text
[user.name@usd.local@login ~]$ export LIBGL_ALWAYS_INDIRECT=1
```
{% endhint %}

All login goes by default to the login node. Do not run compute jobs on the login node! Please read further instructions on how to use Slurm, the Lawrence cluster workload manager.

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh%20%281%29%20%281%29.png)

## Lawrence SSH Login for Linux

Open the command terminal, and ssh into Lawrence.  The output you see will be different depending on how your Duo account is setup.  First is if your account uses 'Push Notification' for your Duo secondary authentication.

```text
username@NI8724:~$ ssh User.Name@Lawrence.usd.edu
Keyboard-interactive authentication prompts from server:
| Password:
| Duo two-factor login for user.name@usd.edu
|
| Enter a passcode or select one of the following options:
|
|  1. Duo Push to XXX-XXX-####
|
| Passcode or option (1-1): 1
| Success. Logging you in...
End of keyboard-interactive prompts from server
```

If you use a Token for your Duo secondary authentication, your login will look more like this

```text
username@NI8724:~$ ssh User.Name@Lawrence.usd.edu
Password: 
Duo two-factor login for user.name@usd.edu

Enter a passcode or select one of the following options:

Passcode: ######
```

{% hint style="info" %}
Note: your **password** will **not show up** as you type and it may look like nothing is happening.  It may seem strange, but keep typing, the remote system is still picking up your keystrokes and when you hit enter your password will be checked. However, the **passcode** you type in from your Duo token **will show up** as you type, this is normal.
{% endhint %}

If it accepts the password, it will show a welcome message and a prompt.

```text
Last login: Tue Aug 20 16:03:26 2019 from 192.236.54.40
Welcome to the Lawrence Supercomputer at the University of South Dakota!
### Other information.... ###
###                       ###
###                       ###
(base) [user.name@usd.local@login ~]$
```

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh%20%281%29.png)

## Lawrence SSH Login for Windows

For video instructions on how to download MobaXterm, click [here](https://usd.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx#folderID=%2243cfe1c4-9acf-4571-add7-aad40134cb34%22).

### Downloading MobaXterm \(MobaX\) terminal

Utilization of the Lawrence cluster by Windows users requires the use of the MobaXterm terminal. MobaXterm can be freely downloaded here \(use the Home Installer Edition\):

[https://mobaxterm.mobatek.net/download.html](https://mobaxterm.mobatek.net/download.html)

![](../.gitbook/assets/screenshot-2-5%20%283%29%20%281%29.png)

{% hint style="warning" %}
If using a **USD issued computer**, you may need **administrative permissions**.  Please contact the ServiceDesk for assistance if these permissions prevent installation of the software.  Make sure to include details like the software name.

**Example**:  "I have recently been provisioned an account on Lawrence, and I am following the tutorial instructions found at the RCG docs site \([https://usdrcg.gitbook.io/docs/lawrence-hpc/login\#lawrence-ssh-login-for-mac](https://usdrcg.gitbook.io/docs/lawrence-hpc/login#lawrence-ssh-login-for-mac)\) to download XQuartz.  My computer is USD issued, and requires administrative permissions to install the software.  Because I don't have this level of access, I would like help in installing this software."
{% endhint %}

Once downloaded, open the MobaX terminal.  Click "Start local terminal".

![](../.gitbook/assets/mobax-startterminal.png)

The command line prompt will appear:

![](../.gitbook/assets/mobax-startterminallogin.png)

### Logging into Lawrence

You can then ssh onto the Lawrence cluster \(same command as Linux/Mac\). 

As a security feature, three incorrect logins will result in your account being locked until the lockout expires or an administrator overrides it.

```text
[2018-11-19 10:55.23]  ~
[User.Name.NI11018] ➤ ssh User.Name@lawrence.usd.edu
User.Name@lawrence.usd.edu's password:
```

{% hint style="info" %}
Note: your **password** will **not show up** as you type- it will look like nothing is happening.  It may seem strange, but keep typing, it is picking up the keystrokes.
{% endhint %}

You will be given a prompt to begin typing commands. All logins go to the login node by default. Do not run compute jobs on the login node! Please read further instructions on how to use Slurm, the Lawrence cluster workload manager.

```text
Last login: Mon Dec 25 19:37:34 2017 from ni11018.usd.local
### Other information.... ###
###                       ###
###                       ###
[user.name@usd.local@login ~]$
```

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh%20%281%29%20%281%29.png)

