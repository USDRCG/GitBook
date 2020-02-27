# Jupyter on Lawrence

## Installing Jupyter

Request a node:

```text
user.name@login ~]$ srun --pty bash
user.name@node02 ~]$
```

Make a directory for Jupyter scripts and cd into it.

```bash
user.name@node02 ~]$ mkdir jupyterScripts
user.name@node02 ~]$ cd jupyterScripts
user.name@node02 jupyterScripts]$
```

Copy the installation and starting scripts into your directory.

```bash
user.name@node02 jupyterScripts]$ cp /apps/jupyter-notebook/* ./
user.name@node02 jupyterScripts]$ ls
install-jupyter-notebook.sh  start-jupyter-notebook.sh
user.name@node02 jupyterScripts]$ 
```

Run the install script.

{% hint style="info" %}
Note: If you would like to **add kernels** to your Jupyter Notebook \(e.g. **R**, **widgets**, etc.\), add the   "**-h"** flag to view options:

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

Use "exit" to exit the node.

```bash
user.name@node02 jupyterScripts]$ exit
user.name@login jupyterScripts]$
```

{% hint style="info" %}
_Why do we request a node for the installation, and then exit out of it to start Jupyter?_

Using another node for the installation process \(`install-jupyter-notebook.sh`\) keeps the login node open for users logging in, however, the script that starts Jupyter `(start-jupyter-notebook.sh)`requests a node \(within the script\), so being in the login node before running it is advised.
{% endhint %}

## Starting Jupyter

\(If you are entering the tutorial here, navigate to the directory that contains "start-jupyter-notebook.sh".\)

Run start-jupyter-notebook.sh using bash.

{% hint style="info" %}
Note: to see **options** **for starting Jupyter**, add an **-h** flag to the command:

* user.name@login jupyter\]$ **bash start-jupyter-notebook.sh -h**
{% endhint %}

```
user.name@login jupyter]$ bash start-jupyter-notebook.sh
```

If you have already opened Jupyter before \(and your password is already set\) you may skip to the "Start Tunnel" section.

### Set a Password

If you are starting Jupyter for the first time, it will prompt you to create a password for your Jupyter Notebook installation. This can be changed or reset at a later time and is not related to your University password.

![Enter your desired password](../.gitbook/assets/image%20%2818%29.png)

{% hint style="info" %}
Note: the cursor will not move as you type- just like when typing the password to log into Lawrence.
{% endhint %}

![Enter your desired password again](../.gitbook/assets/image%20%283%29.png)

### Resetting your Password

If you forget your password and need to reset it:

Open your Jupyter environment.

```text
user.name@usd.local@local jupyterScripts]$ conda activate jupyter
(jupyter) user.name@usd.local@local jupyterScripts]$
```

Then run "jupyter notebook password".  Enter a new password when prompted. \(Remember, the cursor won't move while typing a password.\)

```text
(jupyter) user.name@usd.local@local jupyterScripts]$ jupyter notebook password
Enter password:
Verify password:
[NotebookPasswordApp] Wrote hashed password to /home/usd.local/adison.kleinsasser/.jupyter/jupyter_notebook_config.json
(jupyter) user.name@usd.local@local jupyterScripts]$ 
```

Don't forget to deactivate your environment.

```text
(jupyter) user.name@usd.local@local jupyterScripts]$ conda deactivate
user.name@usd.local@local jupyterScripts]$
```

{% hint style="info" %}
_Why do we bother having a password if it's so easy to reset?_

Once the Jupyter server is started, anyone on Lawrence could theoretically access that Jupyter instance if they know the port it is using. The password protects your Jupyter from being accessible by unauthorized people who would have the same read/write access to any files your running jupyter notebook session can access.
{% endhint %}

### Start Tunnel

After running the `bash start-jupyter-notebook.sh`command \(and setting a password if necessary\), an ssh command and a localhost link will appear in the terminal \(They aren't click-able\).

![](../.gitbook/assets/image%20%2829%29.png)

Copy the ssh command from the print-out. \(**Do not use Ctrl-C**, it'll cut off the job\).

![Don&apos;t use Ctrl-C](../.gitbook/assets/copysshforjupyter.png)

Open a **second terminal**, and paste the command into it.

![](../.gitbook/assets/make-2nd-tunnel.png)

Then hit "Enter".

![](../.gitbook/assets/image%20%285%29.png)

Back in the **first terminal**, copy the localhost link:

![](../.gitbook/assets/image%20%2821%29.png)

Then open a browser, and paste it in the address bar \(Note: your link will likely be **different** from the one shown- **don't copy the one in the picture**\).

![](../.gitbook/assets/image%20%2813%29.png)

Press "Enter", then enter your password when prompted:

![](../.gitbook/assets/image%20%2825%29.png)

and Jupyter will come up.

![](../.gitbook/assets/image%20%2816%29.png)

### Quit Jupyter

When you are done with Jupyter, **don't simply close the browser**.  Make sure you **shut down the server** as well.  Click on the "Quit" button in Jupyter:

![](../.gitbook/assets/image%20%2824%29.png)

The first terminal will then look like this:

![](../.gitbook/assets/image%20%2819%29.png)

Notice that the command prompt has come back.  In the second terminal, use Ctrl-C to bring back the command line.

![](../.gitbook/assets/image%20%2814%29.png)



