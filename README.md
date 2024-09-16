# cuda setup steps for local projects      

2024-09-15  
Ubuntu 24.04.1  

### 1.  
verify nvidia drivers were installed by ubuntu installer:  
`nvidia-smi`  
> `NVIDIA-SMI 550.107.02             Driver Version: 550.107.02     CUDA Version: 12.4`  

### 2.  
sanity check gpu info:  
`lspci | grep -i nvidia`  
> `01:00.0 3D controller: NVIDIA Corporation GP107M [GeForce GTX 1050 Ti Mobile] (rev a1)`  

### 3.  
use miniconda to more easily and flexibly manage cuda and cudnn (be sure to buy a license for commercial projects):  
- download  
`pushd ~`
`curl -O https://repo.anaconda.com/archive/Miniconda3-latest-Linux-x86_64.sh`  
- install  
`curl -O https://repo.anaconda.com/archive/Miniconda3-latest-Linux-x86_64.sh`  
- manually accept license, autorun `conda init`, etc  
- restart  
`source ~/.bashrc`  
- prefer not to activate base env by default (optional)  
`conda config --set auto_activate_base False` 
- use faster env solver  
`conda update -n base conda`  
`conda install -n base conda-libmamba-solver`  
`conda config --set solver libmamba`   
- create conda env  
`conda create -n pytorch-env python=3.11`  
`conda activate pytorch-env`  
- install cudatoolkit  
`conda install -c conda-forge cudatoolkit`
- install cudnn  
`conda install -c conda-forge cudnn`  

### 4.  
install pytorch:  
`conda install pytorch torchvision torchaudio pytorch-cuda=12.4 -c pytorch -c nvidia`  

### 5.  
test:  
`nvcc --version`  
`python`  
`import torch`  
`quit()`