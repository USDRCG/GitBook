# Programming Environment

## Compilers

The Lawrence HPC programming environment has the choice of two compilers: Intel and Gnu 4.8.5 \(gcc\).

## OpenMP

OpenMP Intel, Gnu

## MPI

MPI's available with Lawrence: open MPI, mpich \(ethernet\), and mvapich \(infinaband\), intel impi

| **MPI modules** | Name for loading |
| :--- | :--- |
| Open MPI | openmpi-1.6/gcc |
|  | openmpi-1.6/intel |
|  | openmpi-1.8/gcc |
|  | openmpi-1.8/intel |
|  | openmpi-2.0/gcc |
|  | openmpi-2.0/intel |
| mpich | mpich/gcc |
|  | mpich/intel |
| mvapich | mvapich2-2.2/gcc |
|  | mvapich2-2.2/intel |

```text
[user.name@usd.local@login ~]$ module avail
------------------------------------------- /usr/share/Modules/modulefiles --------------------------------------------
dot         module-git  module-info modules     null        use.own

-------------------------------------------------- /act/modulefiles ---------------------------------------------------
cuda-9.1           intel              mvapich2-2.2/gcc   openmpi-1.6/intel  openmpi-2.0/gcc
gaussian/16        mpich/gcc          mvapich2-2.2/intel openmpi-1.8/gcc    openmpi-2.0/intel
impi               mpich/intel        openmpi-1.6/gcc    openmpi-1.8/intel

```



#### To load a module:

```text
[user.name@usd.local@login ~]$ module load openmpi-2.0/gcc
```

#### To view the module version in use:

```text
[adison.kleinsasser@usd.local@login ~]$ mpirun --version
mpirun (Open MPI) 2.0.1
```

