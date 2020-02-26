# Jupyter on Lawrence

## Installing Jupyter

{% hint style="danger" %}
Note: the instructions for installing Jupyter are currently under construction - proceed at your own risk.
{% endhint %}

Make a directory for Jupyter scripts and cd into it.

```bash
user.name@node02 ~]$ mkdir jupyterScripts
user.name@node02 ~]$ cd jupyterScripts
user.name@node02 jupyterScripts]$
```

Copy the installation and starting scripts into your directory.

```bash
user.name@node02 jupyterScripts]$ cp /home/jennewein_lab/shared/bill/jupyter/* ./
user.name@node02 jupyterScripts]$ ls
install-jupyter-notebook.sh  start-jupyter-notebook.sh  test-ipyparallel.py
user.name@node02 jupyterScripts]$ 
```

Run the install script.

{% hint style="info" %}
Note: If you would like to **add kernels** to your Jupyter Notebook \(e.g. R, widgets, etc.\), use the   **-h** flag to view options:

* user.name@node02 jupyter\]$ **bash install-jupyter-notebook.sh -h**
{% endhint %}

```bash
user.name@node02 jupyterScripts]$ bash install-jupyter-notebook.sh
Creating new environment now...
Collecting package metadata (repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /home/usd.local/adison.kleinsasser/anaconda3/envs/jupyter

  added / updated specs:
    - ipykernel
    - jupyter


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    bleach-3.1.1               |             py_0         111 KB  conda-forge
    gst-plugins-base-1.14.5    |       h0935bb2_2         6.8 MB  conda-forge

```

Follow any instructions that pop up.



## Starting Jupyter

Navigate to the directory that contains start-jupyter-notebook.sh and run the file using bash

{% hint style="info" %}
Note: to see **options** **for starting Jupyter**, add an **-h** flag to the command:

* user.name@node02 jupyter\]$ **bash install-jupyter-notebook.sh -h**
{% endhint %}

```
user.name@login jupyter]$ bash start-jupyter-notebook.sh
```

If you have already opened Jupyter before \(and your password is already set\) you may skip to the "Start Tunnel" section.

### Set a Password

If you are starting Jupyter for the first time, it will prompt you to enter a password:

![Enter your desired password](../.gitbook/assets/image%20%2817%29.png)

{% hint style="info" %}
Note: the cursor will not move as you type- just like when typing the password to log into Lawrence.
{% endhint %}

![Enter y](../.gitbook/assets/image%20%283%29.png)

### Start Tunnel

After running the `bash start-jupyter-notebook.sh`command \(and setting a password if necessary\), an ssh command and a localhost link will appear in the terminal.

![](../.gitbook/assets/image%20%2826%29.png)

Copy the ssh command from the print-out. \(**Do not use Ctrl-C**, it'll cut off the job\).

![Don&apos;t use Ctrl-C](../.gitbook/assets/copysshforjupyter.png)

Open a **second terminal**, and paste the command into it.

![](../.gitbook/assets/make-2nd-tunnel.png)

Then hit "Enter".

![](../.gitbook/assets/image%20%285%29.png)

Back in the **first terminal**, copy the http address:

![](../.gitbook/assets/image%20%2819%29.png)

Then open a browser, and paste it in the address bar

![](../.gitbook/assets/image%20%2813%29.png)

Press "Enter", then enter your password when prompted:

![](../.gitbook/assets/image%20%2822%29.png)

and Jupyter will come up.

![](../.gitbook/assets/image%20%2815%29.png)

