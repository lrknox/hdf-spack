This holds a Spack package to build HDF5 using CMake .  
It relies on Spack and the builtin Spack packages, some of which may be overridden by this repo.

## Getting started

Initial setup for bash-like shells:

```
cd /path/your-working-dir
git clone https://github.com/spack/spack.git
git clone https://github.com/HDFGroup/hdf-spack
source ./spack/share/spack/setup-env.sh
spack repo add ./hdf-spack
spack repo list
```
This repo's packages are now available locally and have precedence over Spack's builtin repo.

The following spack command example will show you which repositories (Namespaces) will be used in a build for a given package before you install it:

```
spack spec -N hdf5
```

The hdf-spack repository contains files for three spack package options: 
hdf5,  hdf5-cmake, and hdf5-autotools.
The hdf5 package is an update to the hdf5 package in the official spack repository
that switches from Autotools to CMake for building HDF5.  Changes can be seen in the
pull request:  https://github.com/spack/spack/pull/18937.

The hdf5-cmake package has most of those updates and also has new variants to enable
these compression filters:
    blosc bshuf bz2 jpeg lz4 lzf szf
    zfp zstd bitgroom mafisc pv av cv
The filters are enabled by default.

The hdf5-autotools package is equivalent to the current hdf5 package in Spack. 

## References: 

This repository contains a collection of [spack](https://spack.io/) packages related to development, building and testing of softwares from The HDF Group [TheHDFGroup](https://www.hdfgroup.org).

For more about spack and what you can do with it, spack has lots of
[documentation](https://spack.readthedocs.io/en/latest/) and a good
[tutorial](https://spack.readthedocs.io/en/latest/tutorial_sc16.html).

This repo uses a local/private repo as described in the Spack Documenation: https://spack.readthedocs.io/en/latest/repositories.html#

There is an active Spack Repo PR in-progress at for the migration of HDF5 for building with CMake.
https://github.com/spack/spack/pull/18937
