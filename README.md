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

### Linux

## Manage the mamba/conda environments:
Default yaml environment description are availbale in the git repository for [windows](https://github.com/vib-bic-code/conda_environments/tree/main/windows).
### Create an environment
- Start a command prompt (Search> `cmd`) or a terminal
- Get a yaml file and store it
- `cd C:\yaml\file\location` or `cd yaml/file/location`
- `mamba env create -f aiscimageio-napari-env.yml`
- See [`env create` options documentations](https://docs.conda.io/projects/conda/en/latest/commands/env/create.html)
  
**_NOTE:_** Environments are by default created in the installation folder in the `envs` subfolder, e.g.  `C:\GBW_MyPrograms\mambaforge\envs\`
### List the environments
- Start a command prompt (Search> `cmd`) or a terminal
- Run the command `mamba env list`
```bash
mamba env list
# conda environments:
#
base                     C:\GBW_MyPrograms\mambaforge
cellpose-omnipose-gpu    C:\GBW_MyPrograms\mambaforge\envs\cellpose-omnipose-gpu
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
- `aiscimageio-napari-env.yml`: the [Napari](https://napari.org) image viewer with the [aiscimageio](https://allencellmodeling.github.io/aicsimageio/) to open different microscopy file format
- `cellpose-gpu-napari-clesperanto.yml`: [cellpose](https://github.com/mouseland/cellpose)/[omnipose](https://omnipose.readthedocs.io/) with the [Napari](https://napari.org)  image viewer with the [aiscimageio](https://allencellmodeling.github.io/aicsimageio/) 
- `pycudadecon-napari-env.yml` : the [Napari](https://napari.org) image viewer with the [pycudadecon](https://github.com/tlambert03/pycudadecon) library to perform Richardson Lucy Deconvolution on GPU
- `stardist-cuda-env.yml` :  [StarDist](https://github.com/stardist/stardist) - Object Detection with Star-convex Shapes on GPU using CUDA
  
for [Windows](https://github.com/vib-bic-code/conda_environments/tree/main/windows) and [<abbr>VSC</abbr> Linux](https://github.com/vib-bic-code/conda_environments/tree/main/vsc-linux)

## Make the environment availbale for a jupyter notebook

###  On the VSC-Linux

#### Activate the environment
```bash
conda activate my_env
```
Where `my_env` in the name of the conda environment

#### Install ipkernel
```bash
conda install ipykernel
```

#### Make the environment available on jupyter notebook
```bash
python -m ipykernel install  --prefix=${VSC_HOME}/.local/ --name 'my_env_name'
```
Where `my_env_name` in the name under which it will appear from the list of availbale kernel
![image](https://github.com/vib-bic-code/conda_environments/assets/1775952/09aa118f-ccba-4265-9dc9-894a355a8296)

It will store the kernel configuration in `${VSC_HOME}/.local/share/jupyter/kernels/my_env_name/`, the configuration of the kernel is detailed in the file `kernel.json`

### Make the environement available and run it on a jupyter notebook on windows
```bash
conda install ipykernel
conda install jupyter
python -m ipykernel install --user --name myenv --display-name "Python (myenv)"
```
```bash
cd D:
cd D:\location\jupyter_notebook
```
```bash
jupyter notebook
```


