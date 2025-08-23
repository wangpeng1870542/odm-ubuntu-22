![Botlab Dynamics Logo](https://botlabdynamics.com/sites/default/files/2022-11/BL%20Botlab%20Dynamics%20%281%29.png)
# Requirements

### Ubuntu 
- Distributor ID:	Ubuntu
- Description:	<b>Ubuntu 22.04.3 LTS</b>
- Release:	22.04
- Codename:	jammy

### Nvidia (Optional)
+---------------------------------------------------------------------------------------+
| NVIDIA-SMI 535.146.02             Driver Version: 535.146.02   CUDA Version: 12.2     |
|-----------------------------------------+----------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
|                                         |                      |               MIG M. |
|=========================================+======================+======================|
|   0  NVIDIA GeForce RTX 4090        Off | 00000000:01:00.0  On |                  Off |
|  0%   39C    P8              15W / 450W |    813MiB / 24564MiB |      0%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+

### Cuda toolkit (Optional)

- <b> Refer to this documentation [https://developer.nvidia.com/cuda-12-2-0-download-archive] </b>

### Configure UbuntuGis

- `sudo apt install -y -qq --no-install-recommends software-properties-common`
- `sudo add-apt-repository -y ppa:ubuntugis/ubuntugis-unstable`
- `sudo apt update`

### Install numpy for default python
- `sudo python3.x -m pip install numpy` (x should be default python3 version check by `python3 --version`)

#### Install python3.8
- `sudo add-apt-repository -y ppa:deadsnakes/ppa`
- `sudo apt install python3.8 python3.8-venv python3.8-dev`

### Switch default python3 to python3.8
- `sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.[x] 1`  (x should be default python3 version check by `python3 --version`)
- `sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 2`
- `sudo update-alternatives --config python3` (select python3.8)

### Install gdal=3.6
- Download [Gdal - Version-3.6](https://github.com/OSGeo/gdal/releases/download/v3.6.4/gdal-3.6.4.tar.gz)
- tar -xvf gdal-3.6.4.tar.gz && gdal-3.6.4
- cd gdal
- mkdir build && cd build
- cmake ..
- make -j
- sudo make install
- sudo python3.8 -m pip install gdal==3.6.4

# Building ODM required libraries
- `./configure.sh install`

## After configuration finished revert default python3 to default ubuntu Python3
- `sudo update-alternatives --config python3` (select default python3 version)

<!--  ## installing odm
- `./configure.sh install`-->

# Running odm
- `./run.sh` (followed with params)

![ODM Logo](https://user-images.githubusercontent.com/1951843/79699889-438ce580-8260-11ea-9c79-8667834aeab2.png)

An open source command line toolkit for processing aerial drone imagery. ODM turns simple 2D images into:

* Classified Point Clouds
* 3D Textured Models
* Georeferenced Orthorectified Imagery
* Georeferenced Digital Elevation Models

![images-diag](https://user-images.githubusercontent.com/1174901/96644651-5b205600-12f7-11eb-827b-8f4a3a6f3b21.png)

The application is available for Linux and it works from the command line, making it ideal for power users, scripts and for integration with other software.

If you would rather not type commands in a shell and are looking for a friendly user interface, check out [WebODM](https://github.com/OpenDroneMap/WebODM).

## Documentation
https://docs.opendronemap.org/


## Credits

ODM makes use of [several libraries](https://github.com/OpenDroneMap/ODM/blob/master/snap/snapcraft.yaml#L36) and other awesome open source projects to perform its tasks. Among them we'd like to highlight:

 - [OpenSfM](https://github.com/mapillary/OpenSfM)
 - [OpenMVS](https://github.com/cdcseacave/openMVS/)
 - [PDAL](https://github.com/PDAL/PDAL)
 - [Entwine](https://entwine.io/)
 - [MVS Texturing](https://github.com/nmoehrle/mvs-texturing)
 - [GRASS GIS](https://grass.osgeo.org/)
 - [GDAL](https://gdal.org/)
 - [PoissonRecon](https://github.com/mkazhdan/PoissonRecon)

 - - ### Versioning done by:
 - - [Om Prakash](https://www.linkedin.com/in/theomprakashprasad/), employed under [Botlab Dymamics](https://botlabdynamics.com/)

## Citation

> *OpenDroneMap Authors* ODM - A command line toolkit to generate maps, point clouds, 3D models and DEMs from drone, balloon or kite images. **OpenDroneMap/ODM GitHub Page** 2020; [https://github.com/OpenDroneMap/ODM](https://github.com/OpenDroneMap/ODM)

## Trademark

See [Trademark Guidelines](https://github.com/OpenDroneMap/documents/blob/master/TRADEMARK.md)


