# Login

{% hint style="warning" %}
**Permission** from the HPC administrator is needed to access Lawrence.  This can be requested by contacting the ServiceDesk.
{% endhint %}

{% hint style="info" %}
* **USD users:** Lawrence login information will be based on your USD login \(e.g. your password will be the same as for your email account\)
* **Non-USD users**: receive an email from the ServiceDesk regarding login information and/or password creation after the account is set up.  

For assistance or to ask questions, please contact the ServiceDesk \(servicedesk@usd.edu\).
{% endhint %}

![](../.gitbook/assets/lawrencediagram2%20%281%29.png)

The Lawrence Supercomputer: Lawrence is composed of a many nodes. The user logs into the login node from their computer. From there they can access many other nodes in order to run analyses. The GPU node is used for graphics processing, and computations involving matrices. The high-memory \(himem\) node contains increased RAM for jobs that require high memory. The VIZ node is used for making visualizations. Besides the special purpose nodes, Lawrence contains 80 computational nodes for data analysis.  The data storage nodes act like a harddrive, albeit much faster, storing the files that are on the user's \(or lab's\) account.  Caution: the storage nodes are not backed up-be sure to back up your files.  The management node is utilized for managing the system.

## Lawrence SSH Login for Mac

### Install XQuartz

{% hint style="warning" %}
If using a USD issued computer, you may need administrative permissions.  Please contact the ServiceDesk for assistance if these permissions prevent installation of the software.
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

Next, login to Lawrence via an ssh session through the login node. 

{% hint style="info" %}
* **USD users:** Lawrence login information will be based on your USD login \(e.g. your password will be the same as for your email account\)
* **Non-USD users**: receive an email from the ServiceDesk regarding login information and/or password creation after the account is set up.  

For assistance or to ask questions, please contact the ServiceDesk \(servicedesk@usd.edu\).
{% endhint %}

```text
ITSCkMac07:~ adison.kleinsasser$ ssh -Y User.Name@lawrence.usd.edu
User.Name@lawrence.usd.edu's password:
```

{% hint style="info" %}
Note: your **password** will **not show up** as you type- it will look like nothing is happening.  It may seem strange, but keep typing, it is picking up the keystrokes.
{% endhint %}

If it accepts the password, it will show a welcome message and a prompt \(a line that ends with '$'\).

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

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh%20%281%29.png)

## Lawrence SSH Login for Linux

{% hint style="info" %}
* **USD users:** Lawrence login information will be based on your USD login \(e.g. your password will be the same as in your email account\)
* **Non-USD users**: receive an email from the ServiceDesk regarding login information and/or password creation after the account is set up.  
{% endhint %}

Open the command terminal, and ssh into Lawrence

```text
username@NI8724:~$ ssh -X User.Name@Lawrence.usd.edu
User.Name@lawrence.usd.edu's password:
```

{% hint style="info" %}
Note: your password won't show up while being typed.
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

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh.png)

## Lawrence SSH Login for Windows

There are two options given in this tutorial for logging into Lawrence on a Windows machine:  Using MobaXterm, or using the Ubuntu terminal.  For the MobaX tutorial, please continue.  For the tutorial using Ubuntu, please skip ahead to the section "Using the Ubuntu terminal".

### Using the MobaXterm terminal

Utilization of the Lawrence cluster by Windows users requires the use of the MobaXterm terminal. MobaXterm can be freely downloaded here \(use the Home Installer Edition\):

[https://mobaxterm.mobatek.net/download.html](https://mobaxterm.mobatek.net/download.html)

![](../.gitbook/assets/screenshot-2-5%20%282%29.png)

Once downloaded, open the MobaX terminal.  Click "Start local terminal".

![](../.gitbook/assets/mobax-startterminal.png)

The command line prompt will appear:

![](../.gitbook/assets/mobax-startterminallogin.png)

### Logging into Lawrence

You can then ssh onto the Lawrence cluster \(same command as Linux/Mac\). 

{% hint style="info" %}
* **USD users:** Lawrence login information will be based on your USD login \(e.g. your password will be the same as in your email account\)
* **Non-USD users**: receive an email from the ServiceDesk regarding login information and/or password creation after the account is set up.  
{% endhint %}

As a security feature, three incorrect logins will result in your account being locked until the lockout expires or an administrator overrides it.

```text
[2018-11-19 10:55.23]  ~
[User.Name.NI11018] ➤ ssh User.Name@lawrence.usd.edu
User.Name@lawrence.usd.edu's password:
Last login: Mon Dec 25 19:37:34 2017 from ni11018.usd.local
[user.name@usd.local@login ~]$
```

{% hint style="info" %}
Note: your **password** will **not show up** as you type- it will look like nothing is happening.  It may seem strange, but keep typing, it is picking up the keystrokes.
{% endhint %}

You will be given a prompt to begin typing commands. All logins go to the login node by default. Do not run compute jobs on the login node! Please read further instructions on how to use Slurm, the Lawrence cluster workload manager.

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh%20%281%29.png)

### Using the Ubuntu terminal

Ubuntu for Windows is available on the Microsoft store.  To begin, search for the Microsoft Store in the search bar in Windows

![](../.gitbook/assets/ubuntu-1%20%282%29.png)

Search for "ubuntu" in the search bar of the store.

![](../.gitbook/assets/ubuntu1%20%281%29.png)

Select the Ubuntu app.

![](../.gitbook/assets/ubuntu2%20%281%29.png)

Click "Get", then "Install".

![](../.gitbook/assets/ubuntu3.png)

#### Logging in

Open the Ubuntu terminal from Start

![](../.gitbook/assets/ubuntuonstart.png)

### Logging into Lawrence

With Ubuntu for Windows open, ssh into Lawrence.

{% hint style="info" %}
* **USD users:** Lawrence login information will be based on your USD login \(e.g. your password will be the same as in your email account\)
* **Non-USD users**: receive an email from the ServiceDesk regarding login information and/or password creation after the account is set up.  
{% endhint %}

{% hint style="info" %}
Note: your **password** will **not show up** as you type- it will look like nothing is happening.  It may seem strange, but keep typing, it is picking up the keystrokes.
{% endhint %}

```text
username@NI8724:~$ ssh -X User.Name@Lawrence.usd.edu
User.Name@lawrence.usd.edu's password:
```

If it accepts the password, it will show a welcome message and a prompt \(a line that ends with '$'\).

```text
Last login: Tue Aug 20 16:03:26 2019 from 192.236.54.40
Welcome to the Lawrence Supercomputer at the University of South Dakota!
### Other information.... ###
###                       ###
###                       ###
(base) [user.name@usd.local@login ~]$
```

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../.gitbook/assets/lawrencediagram2-ssh.png)

