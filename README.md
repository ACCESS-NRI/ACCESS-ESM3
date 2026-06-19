![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FACCESS-NRI%2FACCESS-ESM3%2Fraw%2Fmain%2Fconfig%2Fversions.json&query=%24.access-spack-packages&label=ACCESS-NRI%2Faccess-spack-packages)

![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FACCESS-NRI%2FACCESS-ESM3%2Fraw%2Fmain%2Fconfig%2Fversions.json&query=%24.spack&label=ACCESS-NRI%2Fspack)

![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FACCESS-NRI%2Fbuild-cd%2Fraw%2FHEAD%2Fconfig%2Fsettings.json&query=%24.deployment.Gadi.Release.%5B'0.22'%5D.spack-config&label=ACCESS-NRI%2Fspack-config%20(Gadi))

# ACCESS-ESM3

ACCESS-ESM3 is an atmosphere - ocean - sea ice (- land - ocean_BGC) model under development, consisting of forks of the [MOM6](https://github.com/ACCESS-NRI/MOM6) ocean model (with optional [WOMBAT BGC](https://github.com/ACCESS-NRI/GFDL-generic-tracers)), [CICE6](https://github.com/ACCESS-NRI/CICE) sea ice model and [UM13](https://github.com/ACCESS-NRI/UM13) atmosphere model. 

ACCESS-ESM3 is built and deployed automatically to `gadi` on NCI (see below for details). **In general, most users should start from one of the [ACCESS-CM3 suites](https://github.com/access-nri/access-cm3-configs)**, rather than building from these sources.

## About this repository

This is the Model Deployment Repository for the ACCESS-ESM3 model executable. This repository contains a [spack environment](https://spack.readthedocs.io/en/latest/environments.html) manifest file ([`spack.yaml`](./spack.yaml)) that defines all the essential components of the model, including exact versions of the source code used.

## Releases

Releases are listed [here](https://github.com/ACCESS-NRI/ACCESS-ESM3/releases) and further details on model component versions can be found in the [ACCESS-NRI Model Release Database](https://reporting.access-nri-store.cloud.edu.au/release-provenance/releases). 

## Support

[ACCESS-NRI](https://www.access-nri.org.au) supports ACCESS-ESM3 for the Australian Research Community.

Any questions about ACCESS-NRI releases of ACCESS-ESM3 should be done through the [ACCESS-Hive Forum](https://forum.access-hive.org.au/). See the [ACCESS Help and Support topic](https://forum.access-hive.org.au/t/access-help-and-support/908) for details on how to do this.
