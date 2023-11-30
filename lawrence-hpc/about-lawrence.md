# About Lawrence

**Please Note:** These docs are being updated due to a cluster upgrade and may not be accurate.

The Lawrence Supercomputer was acquired through a combination of state and federal funding: a FY16 SD Board of Regents Research And Development Innovation award, and National Science Foundation Major Research Instrumentation award [OAC-1626516](https://nsf.gov/awardsearch/showAward?AWD\_ID=1626516\&HistoricalAwards=false).

## Overview

Lawrence runs the Rocky8 Linux operating system and is made up of over 2,000 CPU cores, including systems with 1.5TB of memory, GPU accelerators, and over 400TB of shared high-speed data storage accessible via a 56GB FDR Infiniband network. Lawrence has an estimated performance of over 60TFLOPS.

## Specifics

The hardware specifications for Lawrence vary by node and are as follows:

| **Node001-Node080**   |                                  |
| --------------------- | -------------------------------- |
| General compute nodes | 80                               |
| CPUs                  | dual 12-core SkyLake 5000 series |
| RAM                   | 96 GB                            |
| SSD                   | 240 GB                           |

| **Node081-Node085**   |                                       |
| --------------------- | ------------------------------------- |
| General compute nodes | 4                                     |
| CPUs                  | dual 16-core Cascade lake 5000 series |
| RAM                   | 96 GB                                 |
| SSD                   | 240 GB                                |

| **Node086-Node093**   |                                       |
| --------------------- | ------------------------------------- |
| General compute nodes | 8                                     |
| CPUs                  | dual 16-core Ice lake 6000 series     |
| RAM                   | 96 GB                                 |
| SSD                   | 240 GB                                |

| **GPU001**| \_\_                             |
| --------- | -------------------------------- |
| GPU Node  | 1                                |
| CPUs      | dual 12-core SkyLake 5000 series |
| GPUs      | 2x Nvidia Tesla P100 16GB        |
| RAM       | 192GB                            |
| SSD       | 240GB                            |

| **GPU002-GPU006** | \_\_                           |
| --------------- | -------------------------------- |
| GPU Node        | 5                                |
| CPUs            | dual 12-core SkyLake 5000 series |
| GPUs            | 1x Nvidia Tesla V100 32GB        |
| RAM             | 192GB                            |
| SSD             | 240GB                            |

| **GPU007-GPU008** | \_\_                           |
| --------------- | -------------------------------- |
| GPU Node        | 2                                |
| CPUs            | dual 12-core Ice Lake 6000 series |
| GPUs            | 1x Nvidia Ampere A100 80GB       |
| RAM             | 128GB                            |
| SSD             | 240GB                            |

| **Viz001**       |                                  |
| ---------------- | -------------------------------- |
| Viz Node         | 1                                |
| CPUs             | dual 12-core SkyLake 5000 series |
| RAM              | 192GB                            |
| SSD              | 240GB                            |
| Graphics Adapter | Nvidia GTX 1080i 11GB            |

| **Himem001, Himem002** | \_\_                             |
| -------------------- | -------------------------------- |
| Large Memory Node    | 2                                |
| CPUs                 | dual 12-core SkyLake 5000 series |
| RAM                  | 1.5TB                            |
| SSD                  | 2x 240GB, mirrored               |

| **Login01** |                                  |
| ----------- | -------------------------------- |
| Login Node  | 1                                |
| CPUs        | dual 16-core SkyLake 5000 series |
| RAM         | 96GB                             |
| SSD         | 2x 240GB, mirrored               |

| **Login02** |                                  |
| ----------- | -------------------------------- |
| Login Node  | 1                                |
| CPUs        | dual 12-core SkyLake 5000 series |
| RAM         | 96GB                             |
| SSD         | 2x 240GB, mirrored               |

| **Head**        |                                  |
| --------------- | -------------------------------- |
| Management node | 1                                |
| CPUs            | Dual 12-core SkyLake 5000 series |
| RAM             | 96GB                             |
| SSD             | 2x 240GB, mirrored               |

| **Zfs01, Zfs02**                        |                               |
| --------------------------------------- | ----------------------------- |
| Storage nodes                           | 2x ZFS, 432TB Raw total       |
| Storage configuration                   | RAIDZ2 across the 2x 216TB    |
| Primary Network                         | FDR IB, 5:1 over subscription |
| Ethernet in-band management network     | 1GB                           |
| Ethernet out-of-band management network | 1GB                           |
