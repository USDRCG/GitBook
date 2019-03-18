---
description: 'Using Lumerical on Lawrence, through a point-and-click interface'
---

# Lumerical \(FDTD\) on Lawrence GUI Tutorial

{% hint style="warning" %}
To use Lumerical on a Lawrence GUI, you must first have access to use the license.  Please ensure you have access before continuing.
{% endhint %}

This is a step-by-step guide for running Lumerical on a graphical user interface \(GUI\) on Lawrence. 

{% hint style="info" %}
If you have **done this before** on the computer ****you are **currently using,** you may **skip to** the section "Opening Lumerical on a Lawrence GUI".
{% endhint %}

## **Installations**

### Install MobaXterm \(MobaX\)

Go to the MobaXterm website [here](https://mobaxterm.mobatek.net/download-home-edition.html). Click on the "MobaXterm Home Edition v11.1 \(Home Installer Edition\)" button.

![](../.gitbook/assets/screenshot-2-5%20%281%29.png)

### Install TigerVNC

Go to the TigerVNC website [here](https://bintray.com/tigervnc/stable/tigervnc). Click on the first source code link:

![](../.gitbook/assets/tigervnc-download%20%281%29.png)

Click on the installed file, and follow the download wizard.

## First Time Setup

Open MobaXterm \(MobaX\) and log into Lawrence.

```text
[User.NI1111] ➤ ssh User.Name@Lawrence.usd.edu
password: 
Last login: Tue Feb 26 10:36:10 2019 from 192.236.35.187 Welcome to the Lawrence Supercomputer at the University of South Dakota!
.....
[user.name@usd.local@login ~]$
```

![](../.gitbook/assets/screenshot-187.png)

If you haven't made a VNC password before, do this now:

```text
[user.name@usd.local@login ~]$ vncpasswd
Password:
Verify:
```

{% hint style="info" %}
Note: the password will not show when typing.
{% endhint %}

## Opening Lumerical on a Lawrence GUI

In MobaX, open a second terminal by clicking the "+" tab.  This will be used in a moment.

![](../.gitbook/assets/screenshot-116.png)

In the first terminal, begin a batch GUI job.

#### Terminal \#1:

![](../.gitbook/assets/vncmaketunnel-cmd-1lumerical.png)

{% hint style="info" %}
Note: the numbers in job-2965.out **correspond** to the number of the **batch job** in the second line \(the number in your command line will likely be different\).

**If the number from the example above** was typed into the "touch" and "tail" commands, rather than the number from your terminal, and the prompt "\[user.name@usd.local@login ~\]$ " hasn't reappeared, hit **Ctrl-C** to get it back, then **repeat** the "touch" and "tail" commands, using the **number that appears in your terminal**.
{% endhint %}

The tail -f command will print the last few lines of the file, which looks like this:

#### Terminal \#1:

![](../.gitbook/assets/vncmaketunnel2.png)

Copy the ssh command \(it will look like the command **circled in red above**\) and **paste** it into the **second terminal** \(then press "enter"\).  It will then ask for a password. \(This is the password you would use to log in to Lawrence, **not the vnc password**.\)  The password will **not appear** as it is typed in.

#### Terminal \#2:

![](../.gitbook/assets/vncmaketunnel-cmd-1-and-2lumerical.png)

#### VNC Viewer

Open TigerVNC from your start menu, copy the localhost \(it will look like what is circled in blue in command line \#1\), and paste it into the "NVC Viewer: Connection Details" window.  **Click "Connect"**.

![](../.gitbook/assets/cmd1-vnc-viewer%20%281%29.png)

The window will then ask for a password. Type in the **VNC password** you made earlier.

![](../.gitbook/assets/vncwindow-psswd.png)

Your VNC window will then pop up.

![](../.gitbook/assets/vncwindow%20%281%29.png)

Open a new terminal.

![](../.gitbook/assets/screenshot-9%20%281%29.png)

Load the Lumerical-FDTD module.

```text
[user.name@usd.local@node55 ~]$ module load lumerical
[user.name@usd.local@node55 ~]$ module list
Currently Loaded Modulefiles:
  1) lumerical
[user.name@usd.local@node55 ~]$ fdtd-solutions

```

![](../.gitbook/assets/lumericalgui.PNG)

{% hint style="info" %}
If you do this, and receive an error like the one below, follow these steps:
{% endhint %}

![](../.gitbook/assets/fdtd-error.png)

Click "yes" to open your license settings.

![](../.gitbook/assets/fdtd-error.b.png)

Ensure that the server listed is "login".  Change this if needed, and click "ok".

![](../.gitbook/assets/fdtderror2.png)

If it doesn't automatically pop up, try starting fdtd-solutions again. 

```text
[user.name@usd.local@node55 ~]$ fdtd-solutions
```

 If a license error still comes up, it is possible that you don't have access to the license, or that someone else is using the license.  

