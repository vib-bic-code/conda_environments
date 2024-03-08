# Installation on Leuven Workstation for all users

## Install miniforge

1. Download [miniforge for windows](https://github.com/conda-forge/miniforge)
2. Copy the installer to `C:\GBW_MyDownloads`
3. Install for all users so to `C:\GBW_MyPrograms\miniforge3`.
   1. Use all default options
   2. Change the permission (`right click > Properties >Security > Select "Users (GBW---)` , select `Edit` and check on `Modify`

## Install git:
1. Download [git for windows](https://git-scm.com/downloads)
2. Copy the installer to `C:\GBW_MyDownloads`
3. Install it to `C:\GBW_MyPrograms\git`
  1. Use all default options

## Install cellpose 3:
1. Create a text file named cellpose-aiscimageio-napari-gpu-env.yml:
2. Fill it with the following:
```yml
# Install cellpose/omnipose with GUI, napari, aiscimageio
# fix the libxml2 version due to a issue on aiscimageio-napari, see https://github.com/AllenCellModeling/napari-aicsimageio/issues/76
#For pytorch-cuda, check your version https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html
#Compatible with the driver version installed on your computer
# see NVIDIA control panel > System information
# conda env create -f cellpose-aiscimageio-napari-gpu-env.yml
# Test if pytorch cuda is installed properly:
# python -c "import torch;print(torch.cuda.is_available())"
name: cellpose-aiscimageio-napari-gpu
channels:
  - pytorch
  - nvidia
  - conda-forge
dependencies:
  - python==3.11.4
  - pytorch
  - pytorch-cuda=11.8
  - mahotas=1.4.13
  - scikit-image
  - napari==0.4.18
  - napari-aicsimageio==0.7.2
  - napari-czifile2==0.2.7
  - libxml2=2.10.4
  - bioformats_jar
  - pandas
  - seaborn
  - natsort
  - stackview
  - pip
  - pip:
    - cellpose==3.0.4
    - cellpose[gui]
    - fsspec>=2022.7.1
    - openpyxl 
    - aicspylibczi
    - napari-animation
```
3. Create the new conda environement
```bash
conda env create -f cellpose-aiscimageio-napari-gpu-env.yml
```
4. Install the git version which fix a GUI probelm
```bash
pip install git+https://github.com/mouseland/cellpose.git
```
5. Create a `.bat` shorcut to run cellpose from a shorcut:
    1. cellpose GUI 3D:
```bash
call "C:\GBW_MyPrograms\miniforge3\Scripts\activate.bat" "C:\GBW_MyPrograms\miniforge3\envs\cellpose-aiscimageio-napari-gpu"
C:\GBW_MyPrograms\miniforge3\envs\cellpose-aiscimageio-napari-gpu\python.exe -m cellpose --Zstack
```
    ii. cellpose GUI 2D:
```bash
call "C:\GBW_MyPrograms\miniforge3\Scripts\activate.bat" "C:\GBW_MyPrograms\miniforge3\envs\cellpose-aiscimageio-napari-gpu"
C:\GBW_MyPrograms\miniforge3\envs\cellpose-aiscimageio-napari-gpu\python.exe -m cellpose
```
save them as `cellpose3d.bat` and `cellpose2d.bat` in `C:\GBW_MyPrograms\`

