# Downloads

## MobaXterm \(MobaX\)

Go to the MobaXterm website [here](https://mobaxterm.mobatek.net/download-home-edition.html). Click on the "MobaXterm Home Edition v11.1 \(Home Installer Edition\)" button.  After it finishes downloading, click on the zip file button.

![](../.gitbook/assets/mobax1.png)

Extract the files, and double click on the installer.

![](../.gitbook/assets/mobax2.png)

Follow the setup wizard.  To open MobaX, go to the start search bar, and start typing "MobaXterm".

![](../.gitbook/assets/mobax3.png)

## TigerVNC

To run VNC, you will need TigerVNC Viewer, available [here](https://bintray.com/tigervnc/stable/tigervnc).  Download the 64-bit version, shown below.

![](../.gitbook/assets/tigervnc-download.png)

Click on the installed file, and follow the download wizard.

### Setting a VNC Password

Log in to Lawrence using MobaX or another terminal.

```text
[user.name@ ~]$ ssh User.Name@Lawrence.usd.edu
Warning: Permanently added 'lawrence.usd.edu' (RSA) to the list of known hosts.
User.Name@Lawrence.usd.edu's password:

Last login: Wed Jan  9 13:14:19 2019 from 192.236.35.187
Welcome to the Lawrence Supercomputer at the University of South Dakota!
......​

[user.name@usd.local@login ~]$
```

A VNC password needs to be set up \(this only needs to be done **once**\).  Make sure you use **vncpasswd**, **not** **vncpassword.**

{% hint style="info" %}
Note: the password will not show up as you type
{% endhint %}

```text
[user.name@usd.local@login ~]$ vncpasswd
Password:
Verify:
```

It may ask "Would you like to enter a view-only password \(y/n\)?"  The usual response is "n".

## Cyberduck



## PuTTY

Go to [https://www.putty.org/](https://www.putty.org/)

Click the link "here" to go to the download page. 

![](../.gitbook/assets/puttytodownloadlink.png)

Select the 32-bit installer link to download the PuTTY installer.  When the download is complete, click on the button in the bottom left corner of the browser to open the installer.

![](../.gitbook/assets/screenshot-73%20%282%29.png)

Install PuTTY with the installer

![](../.gitbook/assets/screenshot-79.png)

A README file will pop up.  You may ignore it for now while following this tutorial, but you may find the information useful when using PuTTY on your own.

Open a PuTTY window

![](../.gitbook/assets/screenshot-85.png)

## 



