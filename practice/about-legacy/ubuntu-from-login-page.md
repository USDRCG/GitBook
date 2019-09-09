# Ubuntu- from Login page

### Using the Ubuntu terminal

Ubuntu for Windows is available on the Microsoft store.  To begin, search for the Microsoft Store in the search bar in Windows

![](../../.gitbook/assets/ubuntu-1%20%282%29.png)

Search for "ubuntu" in the search bar of the store.

![](../../.gitbook/assets/ubuntu1%20%281%29.png)

Select the Ubuntu app.

![](../../.gitbook/assets/ubuntu2%20%281%29.png)

Click "Get", then "Install".

![](../../.gitbook/assets/ubuntu3.png)

#### Logging in

Open the Ubuntu terminal from Start

![](../../.gitbook/assets/ubuntuonstart.png)

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

![The &quot;ssh User.Name@Lawrence.usd.edu&quot; command is used to login to the &quot;Login node&quot; on Lawrence.](../../.gitbook/assets/lawrencediagram2-ssh.png)



