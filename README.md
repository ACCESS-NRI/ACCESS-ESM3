![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FACCESS-NRI%2FACCESS-ESM3%2Fraw%2Fmain%2Fconfig%2Fversions.json&query=%24.access-spack-packages&label=ACCESS-NRI%2Faccess-spack-packages)

![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FACCESS-NRI%2FACCESS-ESM3%2Fraw%2Fmain%2Fconfig%2Fversions.json&query=%24.spack&label=ACCESS-NRI%2Fspack)

![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FACCESS-NRI%2Fbuild-cd%2Fraw%2FHEAD%2Fconfig%2Fsettings.json&query=%24.deployment.Gadi.Release.%5B'0.22'%5D.spack-config&label=ACCESS-NRI%2Fspack-config%20(Gadi))

# ACCESS-ESM3

ACCESS-ESM3 is an atmosphere - ocean - sea ice (- BGC) model under development, consisting of forks of the [MOM6](https://github.com/ACCESS-NRI/MOM6) ocean model (with optional [WOMBAT BGC](https://github.com/ACCESS-NRI/GFDL-generic-tracers)), [CICE6](https://github.com/ACCESS-NRI/CICE) sea ice model and [UM13](https://github.com/ACCESS-NRI/UM13) atmosphere model. 

ACCESS-ESM3 is built and deployed automatically to `gadi` on NCI (see below for details). **In general, most users should start from one of the [ACCESS-CM3 suites](https://github.com/access-nri/access-cm3-configs)**, rather than building from these sources.

## About this repository

This is the Model Deployment Repository for the ACCESS-ESM3 model executable. This repository contains a [spack environment](https://spack.readthedocs.io/en/latest/environments.html) manifest file ([`spack.yaml`](./spack.yaml)) that defines all the essential components of the model, including exact versions of the source code used.

## Releases

Releases are listed [here](https://github.com/ACCESS-NRI/ACCESS-ESM3/releases) and further details on model component versions can be found in the [ACCESS-NRI Model Release Database](https://reporting.access-nri-store.cloud.edu.au/release-provenance/releases). 

## Support

[ACCESS-NRI](https://www.access-nri.org.au) supports ACCESS-ESM3 for the Australian Research Community.

Any questions about ACCESS-NRI releases of ACCESS-ESM3 should be done through the [ACCESS-Hive Forum](https://forum.access-hive.org.au/). See the [ACCESS Help and Support topic](https://forum.access-hive.org.au/t/access-help-and-support/908) for details on how to do this.


### Build

ACCESS-NRI is using [spack](https://spack.io), a build from source package manager designed for use with high performance computing.

Spack automatically builds all the components and their dependencies, producing model component executables. Spack already contains support for compiling thousands of common software packages. Spack packages for the components are defined in the [spack packages repository](https://github.com/ACCESS-NRI/spack_packages/).

ACCESS-ESM3 is built and deployed automatically to `gadi` on NCI (see below). However it is possible to use spack to compile the model using the `spack.yaml` environment file in this repository. To do so follow the [instructions on for configuring spack on `gadi`](https://access-hive.org.au/getting_started/spack/).

Then clone this repository and run the following commands on `gadi`:

```bash
spack env create access-esm3 spack.yaml
spack env activate access-esm3
spack install
```

to create a spack environment called `access-esm3` and build all the components, the locations of which can be found using `spack find --paths`.

### Deployment

ACCESS-ESM3 is deployed automatically when a new version of the [`spack.yaml`](./spack.yaml) file is committed to `main` or a dedicated `backport/VERSION` branch. All the ACCESS-ESM3 components are built using `spack` on `gadi` and installed under the [`vk83`](https://my.nci.org.au/mancini/project/vk83) project in `/g/data/vk83`. It is necessary to be a member of [`vk83`](https://my.nci.org.au/mancini/project/vk83) project to use ACCESS-NRI deployments of ACCESS-ESM3.

The deployment process also creates a GitHub release with the same tag. All releases are available under the [Releases page](https://github.com/ACCESS-NRI/ACCESS-ESM3/releases). Each release has a changelog and meta-data with detailed information about the build and deployment, including:

- paths on `gadi` to all executables built in the deployment process (`spack.location`)
- a `spack.lock` file, which is a complete build provenance document, listing all the components that were built and their dependencies, versions, compiler version, build flags and build architecture. It is also installable via spack similarly to the `spack.yaml`. 
- the environment `spack.yaml` file used for deployment

Additionally the deployment creates environment modulefiles, the [standard method for deploying software on `gadi`](https://opus.nci.org.au/display/Help/Environment+Modules). To view available ACCESS-ESM3 versions:

```bash
module use /g/data/vk83/modules
module avail access-esm3
```

For users of ACCESS-ESM3 model configurations released by ACCESS-NRI, knowledge of the exact location of the model executables is not required. Model configurations will be updated with new model components when necessary.

For information on contributing your own fixes to the ACCESS-ESM3 `spack.yaml`, see the [Hive Docs article](https://docs.access-hive.org.au/models/run-a-model/create-a-prerelease/) on creating a prerelease.
