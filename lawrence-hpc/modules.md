# Software

The Lawrence HPC uses modules for the use of software applications on the HPC. Modules allow various versions of software to be available, and also allows a way to make new software. This document provides a brief overview of module commands as they pertain to USD's Lawrence HPC.

Once you are logged into Lawrence, the module commands will be available to you. Following is a brief overview of the basic module commands:

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

Anaconda is a channel software manager of conda which can be used for installing various applications.  Anaconda is recommended for those wishing to install software that is not readily available as a module. More information on using Anaconda can be found on the Anaconda documentation page[ __here](https://docs.anaconda.com/anaconda/user-guide/)_._ Packages currently available on Anaconda can be found [here](https://docs.anaconda.com/anaconda/packages/pkg-docs/).  Anaconda provides python by default.  R may be installed using the command "conda install R".

To install Anaconda in your home directory on Lawrence, run the install-anaconda script as follows:

```text
[user.name@usd.local@login ~]$ /apps/install-anaconda.sh
Downloading installer
Running installer
...
Done!
[user.name@usd.local@login ~]$

```

Then run the installer.  Make sure to select "yes" when asked about prepending the Anaconda3 install location to PATH.

```text
[user.name@usd.local@login ~]$ bash anaconda.sh

Welcome to Anaconda3 5.1.0

In order to continue the installation process, please review the license
agreement.
....
Do you accept the license terms? [yes|no]
[no] >>> yes
....
Anaconda3 will now be installed into this location:
/home/usd.local/user.name/anaconda3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below
[/home/usd.local/user.name/anaconda3] >>>
REFIX=/home/usd.local/user.name/anaconda3
installing: python-3.6.4-hc3d631a_1 ...
...
Do you wish the installer to prepend the Anaconda3 install location
to PATH in your /home/usd.local/user.name/.bashrc ? [yes|no]
[no] >>> yes
...
Visual Studio Code License: https://code.visualstudio.com/license

Do you wish to proceed with the installation of Microsoft VSCode? [yes|no]
>>> no
[user.name@usd.local@login ~]$
```

To update your Anaconda3 to the latest version of Anaconda3, type the following command:

```text
[user.name@usd.local@login ~]$ conda update conda && conda update anaconda
```

### Packages

Packages that do not automatically come with Anaconda may be installed using the "install.packages package-name" command.  Package options are available [here](https://docs.anaconda.com/anaconda/packages/pkg-docs/).  R language package options are available [here](https://docs.anaconda.com/anaconda/packages/r-language-pkg-docs/).

```text
[user.name@usd.local@login ~]$ install.packages mpi4py
```

### R

After Anaconda is installed, to install R, use "conda install R":

```text
[user.name@usd.local@login ~]$ conda install R
Solving environment: done
...
xorg-xproto 7.0.31: ########################################################### | 100%
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
[user.name@usd.local@login ~]$
```

Anaconda may also be used to install R packages.  One popular package at USD is R-essentials.  To install this, use the conda install command "conda install -c r r-essentials":

```text
[user.name@usd.local@login ~]$ conda install -c r r-essentials
Solving environment: done

## Package Plan ##

  environment location: /home/usd.local/user.name/anaconda3

  added / updated specs:
    - r-essentials
...
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
[user.name@usd.local@login ~]$
```

## Bioconda

Bioconda is a version of Anaconda \(a channel software manager of conda\) that is designed especially for use in the biological sciences. It can be used for installing various bioinformatics applications. Bioconda is recommended for those wishing to install software that is not readily available as a module, especially in the biological sciences. More information on using Bioconda can be found on the Bioconda documentation page [here](https://bioconda.github.io/). Packages currently available on Bioconda can be found [here](https://bioconda.github.io/recipes.html#recipes).

To install Bioconda in your home directory on Lawrence, run the install-bioconda script as follows:

```text
[user.name@usd.local@login ~]$ /apps/install-bioconda.sh
Downloading installer
Running installer
PREFIX=/home/usd.local/user.name/anaconda3
Installing...
...
Done!
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
