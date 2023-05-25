
## Prerequisites and Dependencies

The following compilers and libraries should be installed as prerequisite.

* cmake
* g++
* gcc
* gfortran
* openmpi

If they are not available on your system, they can be installed with the following commands.

```
sudo apt update
sudo apt install cmake
sudo apt-get install gfortran
sudo apt-get install g++ gcc
sudo apt-get install openmpi-bin openmpi-doc libopenmpi-dev
```

## Build VeloC

```
git clone --single-branch --depth 1 https://github.com/ECP-VeloC/veloc.git

cd veloc/
./bootstrap.sh 
./auto-install.py ~/veloc/
```

## Build NWCHEM

```
export ARMCI_NETWORK=MPI-TS
export NWCHEM_MODULES="md smallqm"
export USE_INTERNALBLAS=y
git clone https://github.com/10eMyrT/veloc-nwchem.git nwchem
cd nwchem
./contrib/distro-tools/build_nwchem
```

To execute a test of NWCHEM, use the following command.

```
cd ~/nwchem/QA/tests/water
mpiexec -n 4 -x LD_LIBRARY_PATH /users/kate01/nwchem/bin/LINUX64/nwchem water_md.nw
```