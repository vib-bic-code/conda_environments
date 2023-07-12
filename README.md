# Conda environments for Bio-Image Analysis
A collection fo yaml file to create conda environments for bio-image analysis

## Mamba installation:
[Mamba](https://github.com/mamba-org/mamba) is a reimplementation of the conda package manager in C++ for much faster dependency solving 

### Windows
- Download the windows installer : https://github.com/conda-forge/miniforge#mambaforge `Mambaforge-Windows-x86_64.exe`
- Start the installer and for KU Leuven windows computer, install it in `C:\GBW_MyPrograms\mambaforge`
- Use the following options:
  - `Create start Menu`
  - `Add Mamforge to my PATH`
  - `Register Mamba Forge as my default Python 3.10`
  - 
### Linux

## Manage the mamba/conda environments:
Default yaml environment description are availbale in the git repository for [windows](https://github.com/vib-bic-code/conda_environments/tree/main/windows).
### Create an environment
- Start a command prompt (Search> `cmd`) or a terminal
- Get a yaml file and store it
- `cd C:\yaml\file\location` or `cd yaml/file/location`
- `mamba env create -f aiscimageio-napari-env.yml`
- See [`env create` options documentations](https://docs.conda.io/projects/conda/en/latest/commands/env/create.html)
### List the environments
- Start a command prompt (Search> `cmd`) or a terminal
- Run the command `mamba env list`
```bash
mamba env list
# conda environments:
#
                         C:\GBW_MyPrograms\Miniconda
base                     C:\GBW_MyPrograms\mambaforge
cellpose-omnipose-gpu     C:\GBW_MyPrograms\mambaforge\envs\cellpose-omnipose-gpu
cellpose-omnipose-gpu2     C:\GBW_MyPrograms\mambaforge\envs\cellpose-omnipose-gpu2
devbio-napari            C:\GBW_MyPrograms\mambaforge\envs\devbio-napari
napari-aicsimageio       C:\GBW_MyPrograms\mambaforge\envs\napari-aicsimageio
pycudadecon-napari       C:\GBW_MyPrograms\mambaforge\envs\pycudadecon-napari
stardist                 C:\GBW_MyPrograms\mambaforge\envs\stardist
```
See [`env list` options documentation](https://docs.conda.io/projects/conda/en/latest/commands/env/list.html)
### Activate an environment
- Start a command prompt (Search> `cmd`) or a terminal
- Run the command `mamba activate napari-aicsimageio`
```bash
mamba activate napari-aicsimageio
(napari-aicsimageio) C:\
```
**_NOTE:_** By default, if an environement is already activated, the previous one will be replaced by the new one.

## Bio Image Analysis mamba/conda environments:
- [Windows](https://github.com/vib-bic-code/conda_environments/tree/main/windows)
- [Linux](https://github.com/vib-bic-code/conda_environments/tree/main/linux)
