---
layout: page
title: Docker images for IPOL
no_groups: true
caption: Docker images for IPOL
description: Docker images for IPOL

---

Any docker images can be used to build a demo. For example, one can use [a python base image](https://hub.docker.com/_/python) or [a debian base image](https://hub.docker.com/_/debian).

However, IPOL also proposes a few prebuilt images for Python demos (recommended):
- `ipol:v1-py3.7`
- `ipol:v1-py3.7-pytorch`
- `ipol:v1-py3.7-tensorflow`
- `ipol:v1-py3.8`
- `ipol:v1-py3.8-pytorch`
- `ipol:v1-py3.8-tensorflow`
- `ipol:v1-py3.9`
- `ipol:v1-py3.9-pytorch`
- `ipol:v1-py3.9-tensorflow`
- `ipol:v1-octave`

# ipol:v1-py*

Each image is based on the dockerhub `python:3.x` image, which itself is based on Debian bullseye.
The images also contain [quarto v0.9.106](https://github.com/quarto-dev/quarto-cli/releases/tag/v0.9.106).

## System packages

The following packages are preinstalled in every IPOL images, in addition to what is already installed in the `python:3.x` base image:
```
cmake
libtiff5-dev
libjpeg-dev
libpng-dev
libfftw3-dev
liblapack-dev
libblas-dev
libopenblas-base
libopenblas-dev
libblas-dev
libblas3
liblapack-dev
liblapacke-dev
liblapacke
libconfig9
libconfig-dev
libconfig++-dev
```

## py3.7

Includes the following additional Python packages from PIP:
```
pip==22.0.4

numpy==1.21.5
scipy==1.7.3
scikit-image==0.19.2
scikit-learn==1.0.2
opencv-contrib-python-headless==4.5.5.64

pillow==9.0.1
iio==0.0.3
imageio==2.16.1
imagecodecs==2021.11.20

jupyter==1.0.0
matplotlib==3.5.1
plotly==5.6.0
pandas==1.3.5

papermill==2.3.4
```

## py3.8

Includes the following additional Python packages from PIP:
```
pip==22.0.4

numpy==1.22.3
scipy==1.8.0
scikit-image==0.19.2
scikit-learn==1.0.2
opencv-contrib-python-headless==4.5.5.64

pillow==9.0.1
iio==0.0.3
imageio==2.16.1
imagecodecs==2021.11.20

jupyter==1.0.0
matplotlib==3.5.1
plotly==5.6.0
pandas==1.4.1

papermill==2.3.4
```

## py3.9

Includes the following additional Python packages from PIP:
```
pip==22.0.4

numpy==1.22.3
scipy==1.8.0
scikit-image==0.19.2
scikit-learn==1.0.2
opencv-contrib-python-headless==4.5.5.64

pillow==9.0.1
iio==0.0.3
imageio==2.16.1
imagecodecs==2021.11.20

jupyter==1.0.0
matplotlib==3.5.1
plotly==5.6.0
pandas==1.4.1

papermill==2.3.4
```

## -pytorch

This flavor adds the following packages (from https://download.pytorch.org/whl/cpu/torch_stable.html):
- `torch==1.11.0+cpu`
- `torchvision==0.12.0+cpu`
- `torchaudio==0.11.0+cpu`

## -tensorflow

This flavor adds the following package:
- `tensorflow-cpu==2.8.0`

# ipol:v1-octave

This image is based on `debian:bullseye` with the following packages:
```
octave
octave-image
octave-signal
octave-control
octave-io
octave-optim
octave-statistics 
```

Octave is at version 6.2.0. The packages are not loaded by default, so you must use `pkg load image` in your code for example.
