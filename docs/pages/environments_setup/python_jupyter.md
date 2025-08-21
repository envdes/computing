# Python and Jupyter

Zhonghua Zheng, last update: 2023/02/28

## Introduction

Here we would use Jupyter notebook on HPC.

You can find a different version for CSF3 [here](https://ri.itservices.manchester.ac.uk/csf3/software/applications/jupyter-notebook/) 

## Prerequisites

Make sure you have a conda environment ("partmc") available.

If the "partmc" conda environment is not available, please follow the "**Conda Installation**"

## use Jupyter notebook on HPC with a GPU

**step 0: submit an interactive job**

Here we use the compute node to intall the conda environment ([ref](https://ri.itservices.manchester.ac.uk/csf3/batch/qrsh/))

```bash
$ srun -p interactive -n 4 -t 0-1 --pty bash
```

**step 1: run the following script**

Please change the partition and gpu configuration accordingly

```bash
#!/bin/bash
source activate partmc
echo "ssh -N -L 8880:`hostname -i`:8880 $USER@csf3.itservices.manchester.ac.uk"
jupyter notebook --port=8880 --no-browser --ip=`hostname -i`
```
**step 2: launch a new terminal, copy and paste the command printed by the "echo" command, and log in**

**step 3: open your browse (e.g., Google Chrome), type `https://localhost:8880`**

## Trouble Shooting 

GPU relevant command

```bash
$ lspci | grep -i nvidia
$ nvidia-smi
```

kill session:

```bash
$ ps -u your_netid -f | grep ssh
$ kill -9 session_id
```

for nfs:

```bash
$ lsof | grep nfs00000
$ kill -9 session_id
```
