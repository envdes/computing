# Conda Installation

Zhonghua Zheng, last update: 2023/02/27

## Introduction

Here we would install Conda and create our first conda environment "partmc"

## submit an interactive job

Here we use the compute node to intall the conda environment ([ref](https://ri.itservices.manchester.ac.uk/csf3/batch/qrsh/))

```bash
$ qrsh -l short
```

## download and activate conda

```bash
# Download and install conda
$ cd $HOME
$ wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
$ chmod +x Miniconda3-latest-Linux-x86_64.sh
$ ./Miniconda3-latest-Linux-x86_64.sh

###### important ######
# Edit .bash_profile or .bashrc, add ":$HOME/miniconda3/bin"
# assume the original one is "PATH=$PATH:$HOME/.local/bin:$HOME/bin" 
# then we would have 
# "PATH=$PATH:$HOME/.local/bin:$HOME/bin:$HOME/miniconda3/bin" 
########################

# Activate the conda system, depends on which one you edited 
$ source .bash_profile
$ source .bashrc
```

## create and activate a conda environment

### option 1: install the environment manually

```bash
# assume we want to create an environment named "partmc", with Python version 3.8

# we only need to create the environment once
$ conda create -n partmc python=3.8

# activate this conda environment 
# we would do this everytime 
$ source activate partmc

# assume we want to install some useful Python packages, e.g., numpy, pandas, scipy, scikit-learn, netcdf4, xarray, matplotlib, jupyterlab
$ conda install -c conda-forge numpy pandas scipy scikit-learn netcdf4 xarray matplotlib jupyterlab
# assume we want to install something that is not available in conda-forge
# Please update to the most recent version of xgboost. 
$ pip install xgboost==1.1.1
```

### option 2: install the environment using a file

create a file, rename it to be "environment.yml"

NOTE: Please update to the most recent version of xgboost.

```
channels:
- conda-forge
- defaults

dependencies:
- python=3.8.0
- numpy
- pandas
- scipy
- scikit-learn
- netcdf4
- xarray
- matplotlib
- jupyterlab
- ipykernel
- ipywidgets
- pip
- pip:
  - xgboost==1.1.1
name: partmc
```

then run the commands

```bash
# Create an environment "partmc" and install the necessary packages
$ conda env create -f environment.yml
# Activate the "partmc" environment
$ source activate partmc
```

