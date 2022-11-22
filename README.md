# CoLoRe-apptainer

Part of this project is [apptainer](https://apptainer.org/) recipe file formalizing build of [CoLoRe](https://github.com/damonge/CoLoRe) as a containerized application.

## Build

```
sudo apptainer build --force ./image.sif ./container.def &> buildout.log
```

## Run

```
mpirun -np 4 CoLoRe_b2022-11-21.sif CoLoRe examples/param.cfg
```

contains openmpi 4.1.4 so it's reasonable to use _similar_ version of openMPI outside of container.

other ingredients:
- cfitsio 4.2.0 
- Healpix 3.82
- gsl 2.7.1
- fftw 3.3.10
- HDF5 from Rocky8 distribution
