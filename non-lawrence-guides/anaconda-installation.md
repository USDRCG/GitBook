---
description: >-
  This page contains instructions for installing Anaconda/Bioconda on Windows,
  Ubuntu on Windows, Mac, a Lawrence account, and Jetstream
---

# Software Installations on Windows

{% hint style="danger" %}
Warning: this site is under construction.  The information may be incomplete.
{% endhint %}

## Anaconda on Windows

To download Anaconda, go to the distribution website: [https://www.anaconda.com/distribution/](https://www.anaconda.com/distribution/).

![](../.gitbook/assets/screenshot-16.png)

Scroll down to the download section.  Select "Windows", then select "Download".

![](<../.gitbook/assets/screenshot-19 (1).png>)

Follow the installation wizard.

![](../.gitbook/assets/anacondainstallationsteps.png)

The Users Guide should pop up ([this](http://docs.anaconda.com/anaconda/user-guide/getting-started/#open-nav-win) webpage).

![](../.gitbook/assets/screenshot-34.png)

To open Anaconda, go to the start menu and expand the Anaconda3 folder.

![](../.gitbook/assets/screenshot-35.png)

Select "Anaconda Navigator".

![](../.gitbook/assets/screenshot-36.png)

![](../.gitbook/assets/screenshot-37.png)

## Anaconda on Ubuntu on Windows

### Installing Ubuntu on Windows

Ubuntu for Windows can be downloaded from the Microsoft store. &#x20;

![](<../.gitbook/assets/ubuntu-1 (4) (4) (4) (4) (4) (4).png>)

Search for "ubuntu".

![](<../.gitbook/assets/ubuntu1 (1).png>)

Select the app.

![](<../.gitbook/assets/ubuntu2 (1) (1) (1) (1) (1) (1).png>)

Click "**Get**", then "**Install**".

![](<../.gitbook/assets/ubuntu3 (2) (2) (2) (2) (2) (2).png>)

![](../.gitbook/assets/ubuntu4.png)

Search for "Ubuntu" and select the app.

![](../.gitbook/assets/screenshot-264.png)

The window will look like this:

![](../.gitbook/assets/screenshot-265.png)



### Installing Anaconda on Ubuntu on Windows

First, open Ubuntu for Windows (see above) and check to ensure that conda is not already installed.&#x20;

```
user@NI0000:~$ which conda
```

If it has been, a file path will show up under the command, if not, the next line will be a prompt.

![](../.gitbook/assets/condanotinstalled.png)

Download the installer

```
user@NI0000:~$ wget --quiet --no-check-certificate https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64
.sh
user@NI0000:~$ ls
Miniconda3-latest-Linux-x86_64.sh

```

Run the installer

```
user@NI0000:~$ bash Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/anaconda3
```

```
PREFIX=/home/adison/anaconda3
Unpacking payload ...
…
  zstd               pkgs/main/linux-64::zstd-1.3.7-h0b5b093_0
…
Preparing transaction: done
Executing transaction: done
installation finished.
…

user@NI0000:~$
```

Run an update:

```
user@NI0000:~$ $HOME/anaconda3/bin/conda update conda -y
```

```
Collecting package metadata (current_repodata.json): done
Solving environment: done
 ...

Executing transaction: done
user@NI0000:~$
```

Then install Anaconda

```
user@NI0000:~$ $HOME/anaconda3/bin/conda install anaconda -y
```

```
Collecting package metadata (current_repodata.json): done
Solving environment: done
 
## Package Plan ##
...
Verifying transaction: done
Executing transaction: / b'Enabling notebook extension jupyter-js-widgets/extension...\n      - Validating: \x1b[32mOK\x1b[0m\n'                                                                                                              done
user@NI0000:~$
```

Initialize

```
user@NI0000:~$ $HOME/anaconda3/bin/conda init
```

```
no change     /home/user/anaconda3/condabin/conda
...
no change     /home/user/anaconda3/etc/profile.d/conda.csh
modified      /home/user/.bashrc
 
==> For changes to take effect, close and re-open your current shell. <==
 
user@NI0000:~$
```

Close and re-open your Ubuntu command line.

## Bioconda on Windows on Ubuntu

After running the installation of Anaconda on Ubuntu on Windows (see above), add bioconda:

```
user@NI0000:~$ conda config --add channels bioconda
```











