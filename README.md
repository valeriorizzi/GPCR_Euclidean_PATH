# RMSD and Euclidean PATH for GPCR activation

<div align="center">
<img src="./adrenaline_lipids_notmoving.gif" width="250"> 
</div>

This repository contains the input files from the following paper

> [A Transferable and Robust Computational Framework for Class A GPCR Activation Free Energies](https://doi.org/the_doi_of_the_publication)

The directories contain the minimum input files necessary to run the APO ADRB1 receptor with the Euclidean path (`ADRB1_APO_euclidean_PATH`), and the MUOR receptor with both the Euclidean (`MUOR_APO_euclidean_PATH`) and the RMSD (`MUOR_APO_old_RMSD_PATH`) paths. Each of these directories contain the topology information of the system, a `.tpr` GROMACS binary file already set at 1 µs, and all the necessary plumed files with the corresponding reference PDBs. The version reported here was implemented in GROMACS 2023 and plumed-2.9.1. The run is organized as eight parallel communicating replicas and can be run with something like
```
mpirun -n 8 gmx_mpi mdrun -deffnm prd -notunepme -pin on -multidir ./0 ./1 ./2 ./3 ./4 ./5 ./6 ./7 -hrex -replex 5000 -plumed plumed.dat
```
For further information please read the corresponding paper or write to the authors.
