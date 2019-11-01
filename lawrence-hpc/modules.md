# Software on Lawrence

The Lawrence HPC uses modules for the use of pre-installed software applications on the HPC. Modules allow various versions of software to be available. This document provides a brief overview of module commands as they pertain to USD's Lawrence HPC.

Once you are logged into Lawrence, the module commands will be available to you. Following is a brief overview of the basic module commands:

{% hint style="info" %}
Modules are for software that have been installed on Lawrence as a whole.  If you have **installed** software in your **own account** \(e.g. through Anaconda/Bioconda\), it will be ready without being loaded.
{% endhint %}

| _Command_ | _Description_ |
| :--- | :--- |
| module avail | show all modules that are available on the system |
| module load SOME.APP | load the listed application \(as long as it is available\) |
| module unload SOME.APP | unload a previously loaded module |
| module list | list the modules you have loaded |
| module help | gives you information regarding the module command |

The following example uses module commands to load R version 3.4.1 and then open R for command line use on Lawrence:

```text
[user.name@usd.local@login ~]$ module avail
r/3.4.1
[user.name@usd.local@login ~]$ module load r/3.4.1 
[user.name@usd.local@login ~]$ R

R version 3.4.1 (2017-06-30) -- "Single Candle"
Copyright (C) 2017 The R Foundation for Statistical Computing
Platform: x86_64-pc-linux-gnu (64-bit)

>
```

## Anaconda

Anaconda is a channel software manager of conda which can be used for installing various applications.  Anaconda is recommended for those wishing to install software that is not readily available as a module. More information on using Anaconda can be found on the Anaconda documentation page[ __here](https://docs.anaconda.com/anaconda/user-guide/)_._ Packages currently available on Anaconda can be found [here](https://docs.anaconda.com/anaconda/packages/pkg-docs/).  Anaconda provides python by default.  **R may be installed** using the command "**conda install R**".

To install Anaconda in your home directory on Lawrence, **connect to a node**, then **run the install-anaconda script** as follows:

```text
[user.name@usd.local@login ~]$ srun --pty bash
[user.name@usd.local@node10 ~]$ /apps/install-anaconda.sh
Downloading installer
Running installer
...
Done!
[user.name@usd.local@node10 ~]$

```

Then run the installer.  Make sure to select **"yes"** when asked about prepending the Anaconda3 install location to PATH.

```text
[user.name@usd.local@node10 ~]$ bash Miniconda3-latest-Linux-x86_64.sh

Welcome to Miniconda3 4.7.10

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>>
```

Click "enter" to continue through the license.  \(You may need to click "enter" multiple times.\)

**Accept** the terms:

```text
....
Do you accept the license terms? [yes|no]
[no] >>> yes
....
```

Then click **"enter"** to accept the installation location when asked.

```text
Miniconda3 will now be installed into this location:
/home/usd.local/user.name/miniconda3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below
[/home/usd.local/user.name/anaconda3] >>>
PREFIX=/home/usd.local/user.name/anaconda3
...
```

Let the installer initialize Miniconda3.

`Do you wish the installer to initialize Miniconda3 by running conda init? [yes|no] [no] >>>yes` 

You may need to **re-open your terminal** for changes to take effect, before continuing

```text
==> For changes to take effect, close and re-open your current shell. <==

If you'd prefer that conda's base environment not be activated on startup,
   set the auto_activate_base parameter to false:

conda config --set auto_activate_base false

Thank you for installing Miniconda3!
[user.name@usd.local@node10 ~]$
```

Check to make sure that conda is installed:

```text
[user.name@usd.local@login ~]$ which conda
~/miniconda3/bin/conda
```

Then update your Miniconda to the latest version of Anaconda3:

```text
[user.name@usd.local@node10 ~]$ conda update conda && conda update anaconda
```

{% hint style="info" %}
Note: **`conda update conda`** may also be used to update Anaconda/Bioconda later.
{% endhint %}

### Packages

Packages that do not automatically come with Anaconda may be installed using the "conda install package-name" command.  Package options are available [here](https://docs.anaconda.com/anaconda/packages/pkg-docs/).  R language package options are available [here](https://docs.anaconda.com/anaconda/packages/r-language-pkg-docs/) \(see the "R" section for installation details for R packages\).

```text
[user.name@usd.local@node10 ~]$ conda install mpi4py
```

### R

After Anaconda is installed, to install R, use "conda install R":

```text
[user.name@usd.local@node10 ~]$ conda install R
Solving environment: done
...
xorg-xproto 7.0.31: ########################################################### | 100%
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
[user.name@usd.local@node10 ~]$ which R

```

MRO \(Microsoft R Open\) is also available, and provides threading.

Anaconda may also be used to install R packages.  One popular package at USD is R-essentials.  To install this, use the conda install command "conda install -c r r-essentials":

```text
[user.name@usd.local@node10 ~]$ conda install -c r r-essentials
Solving environment: done

## Package Plan ##

  environment location: /home/usd.local/user.name/anaconda3

  added / updated specs:
    - r-essentials
...
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
[user.name@usd.local@node10 ~]$
```

## Bioconda

Bioconda is a version of Anaconda \(a channel software manager of conda\) that is designed especially for use in the biological sciences. It can be used for installing various bioinformatics applications. Bioconda is recommended for those wishing to install software that is not readily available as a module, especially in the biological sciences. More information on using Bioconda can be found on the Bioconda documentation page [here](https://bioconda.github.io/). Packages currently available on Bioconda can be found [here](https://bioconda.github.io/recipes.html#recipes).

To install Bioconda in your home directory on Lawrence, connect to a node, then run the install-bioconda script as follows:

```text
[user.name@usd.local@login ~]$ srun --pty bash
[user.name@usd.local@node10 ~]$ /apps/install-bioconda.sh
Downloading installer
Running installer
PREFIX=/home/usd.local/user.name/anaconda3
Installing...
...
Done!
```

There will be a **.sh** file in your home directory. Run this using bash.

```text
[user.name@usd.local@node10 ~]$ ls
anaconda3  Miniconda3-latest-Linux-x86_64.sh  perl5
[user.name@usd.local@node10 ~]$ bash Miniconda3-latest-Linux-x86_64.sh

Welcome to Miniconda3 4.7.10

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue

```

Press **enter** to continue, and to scroll through the license, then type "**yes**" to accept the license.

```text
Do you accept the license terms? [yes|no]
[no] >>> yes

Miniconda3 will now be installed into this location:
/home/usd.local/user.name/miniconda3
```

Press **enter** to confirm the installation location.

```text
  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/usd.local/user.name/miniconda3] >>>
```

Type "**yes**" to allow the installer to run `conda init`

```text
Do you wish the installer to initialize Miniconda3
by running conda init? [yes|no]
[no] >>> yes
```

Wait for the installation to finish.  Your command prompt will reappear to show that the computer is ready.

```text
Thank you for installing Miniconda3!
[user.name@usd.local@node10 ~]$
```

**Log** **out** of the node and Lawrence**, then back into** Lawrence for the changes to take effect.

```text
[user.name@usd.local@node10 ~]$ exit
[user.name@usd.local@login ~]$ exit
exit
[MyName.NI1111] ➤ ssh user.name@Lawrence.usd.edu
...
[user.name@usd.local@login ~]$ which conda
~/miniconda3/bin/conda
```

Bioconda will now be available through your home directory to install software. It will appear as "Anaconda"

After Bioconda is installed, to install R, use "conda install R" \(see instructions above: _Anaconda - R_\)

## Math Libraries

### Intel Math Kernel Library \(MKL\)

The Intel MKL library is available on Lawrence and is the recommended math library for most applications. This library is configurable to various compilers and languages. Functions provided by Intel MKL include BLAS, LAPACK, and FFTW. For more information on Intel MKL, please visit the developer documentation [webpage](https://software.intel.com/en-us/mkl/documentation).

Intel also provides a tool to generate appropriate command line options for your particular compiler, integer size, and threading model which can be found [here](https://software.intel.com/en-us/articles/intel-mkl-link-line-advisor).

Example command line options for C and GCC compilers can be found below. These commands would be added after running "module load intel":

Intel C compiler:

```text
-DMKL_ILP64 -I${MKLROOT}/include  -L${MKLROOT}/lib/intel64 -lmkl_intel_ilp64 -lmkl_sequential -lmkl_core -lpthread -lm -ldl
```

GCC C compiler:

```text
-DMKL_ILP64 -m64 -I${MKLROOT}/include -L${MKLROOT}/lib/intel64 -Wl,--no-as-needed -lmkl_intel_ilp64 -lmkl_sequential -lmkl_core -lpthread -lm -ldl
```

