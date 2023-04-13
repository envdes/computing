# Interactive Jobs on Bede

Zhonghua Zheng, last update: 2023/04/13

## Introduction

Currently [Bede](https://bede-documentation.readthedocs.io/en/latest/index.html) documentation doens't provide the instruction for interactive jobs (e.g. Jupyter Notebook).

Here we would request resources for interactive jobs on [Bede](https://bede-documentation.readthedocs.io/en/latest/index.html).

Step 1: Follow the guideline [here](https://bede-documentation.readthedocs.io/en/latest/usage/index.html#requesting-resources) (e.g., partition, time, etc.) and run the command `salloc` to request allocation 

```bash
$ salloc --nodes=1 --account=<project> --partition=<partition> --time=00:30:00
```

And you can check the hostname of the GPU by typing

```
$ srun hostname
```

You can also check the hostname of the login node by typing

```bash
$ hostname
```

Step 2: Then you can establish the interactive session by using

```
$ srun --pty bash 
```

## Next

- Please follow [HERE](./conda_env.md) to install conda, note the difference is we should use `ppc64le` (by typing `arch` instead of `x86_64`

  ```bash
  $ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-ppc64le.sh
  $ chmod +x Miniconda3-latest-Linux-ppc64le.sh
  $ ./Miniconda3-latest-Linux-ppc64le.sh
  ```

  The instruction of conda installation is available [HERE](https://bede-documentation.readthedocs.io/en/latest/software/applications/conda.html)

- When run the jupyter notebook on Bede

  ```bash
  $ echo "ssh -N -L 8880:`hostname -i`:8880 $USER@login1.bede.dur.ac.uk"
  $ jupyter notebook --port=8880 --no-browser --ip=`hostname -i`
  ```

## Reference

- [High Performance Computing (HPC) documentation of the University of Bern](https://hpc-unibe-ch.github.io/slurm/interactive-jobs.html)
- [LUMI supercomper user guide](https://docs.lumi-supercomputer.eu/runjobs/scheduled-jobs/interactive/)
