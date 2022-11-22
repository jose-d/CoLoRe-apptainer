# CoLoRe-apptainer

Part of this project is [apptainer](https://apptainer.org/) recipe file formalizing build of [CoLoRe](https://github.com/damonge/CoLoRe) as a containerized application.

## Build

1) git clone this repo;

2) (possibly modify `CoLoRe_Makefile` to your liking )

3) build:

```
sudo apptainer build --force ./CoLoRe.sif ./container.def &> buildout.log
```

Tested with apptainer 1.0.3-1 on Rocky Linux 8.

## Run

CoLoRe is installed into `/usr/local/bin/CoLoRe` inside of container, so it can be started so easy:

```
mpirun -np 4 CoLoRe.sif CoLoRe examples/param.cfg
```

contains openmpi 4.1.4 so it's reasonable to use _similar_ version of openMPI outside of container to ensure [hybrid MPI](https://apptainer.org/docs/user/main/mpi.html) model will work properly.

other ingredients:
- cfitsio 4.2.0 
- Healpix 3.82
- gsl 2.7.1
- fftw 3.3.10
- HDF5 from Rocky8 distribution
