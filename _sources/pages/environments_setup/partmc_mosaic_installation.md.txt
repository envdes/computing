PartMC-MOSAIC Installation
======

Last update: 2023/07/16

## **build MOSAIC chemistry** 

MOSAIC is not publicaly available, you'll first get the `mosaic.zip` from Dr. Zhonghua Zheng

step 1: unzip `mosaic.zip` and upload `mosaic` folder to your path

step 2: run the following commands

```bash
$ module load tools/env/proxy
$ module load libs/gcc/netcdf/4.6.2 tools/gcc/cmake/3.23.0
$ cd /your_mosaic_path
$ cp Makefile.local.gfortran Makefile.local
$ make
```

## build and test PartMC-MOSAIC

please type `pwd` to record /your_mosaic_path  

step 1: run the following commands

```bash
$ module load tools/env/proxy
$ module load libs/gcc/netcdf/4.6.2 tools/gcc/cmake/3.23.0
$ cd your_path
$ mkdir partmc
$ cd partmc
$ wget https://github.com/compdyn/partmc/releases/download/2.6.1/partmc-2.6.1.tar.gz
$ tar zxvf partmc-2.6.1.tar.gz
$ cd partmc-2.6.1
$ mkdir build
$ cd build
# Note: when export MOSAIC_HOME, there are no quotation marks. And you MUST include "/" in the end of your_mosaic_path
$ export MOSAIC_HOME=/your_mosaic_path/ 
$ ccmake -DCMAKE_INSTALL_PREFIX=/opt/apps/apps/gcc/partmc/partmc-2.6.1 ..
```

step 2: 

- you'll see "EMPTY CACHE", press "c"
- press "e"
- modify the following options:

```
CMAKE_BUILD_TYPE: RELEASE
ENABLE_MOSAIC: ON 
```

- press "c"
- press "e"
- press "c"
- press "e"
- press "g"

step 3: compile and make sure you have all the test cases such as "test_mosaic" passed.

```bash
make
make test
```

Now you are all set!

## Running PartMC and PartMC-MOSAIC

```bash
# PartMC only
$ module load apps/gcc/partmc/2.6.1
# PartMC-MOSAIC
$ module load apps/gcc/partmc-mosaic/22.0
```

## More Information about PartMC and PartMC-MOSAIC on CSF3

PartMC-MOSAIC related

- https://ri.itservices.manchester.ac.uk/csf3/software/applications/partmc/
- https://ri.itservices.manchester.ac.uk/csf3/software/applications/partmc/partmc-mosaic/

Job-arrays

- https://ri.itservices.manchester.ac.uk/csf3/batch/job-arrays/

Job dependencies

- https://ri.itservices.manchester.ac.uk/csf3/batch/job-dependencies/

Training course and loading the training exercise

- https://ri.itservices.manchester.ac.uk/course/rcsf/
- `$module load training/RCSF`

## Contributors

- Constantinos Katsamis (for PartMC and PartMC-MOSAIC) 
- Zhonghua Zheng (for PartMC and PartMC-MOSAIC)
- Jeffrey Curtis 
