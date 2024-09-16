docs on setup steps for local projects      

2024-09-15  
Ubuntu 24.04.1  

1.  
nvidia drivers are installed by ubuntu installer:  
`nvidia-smi`  
> `NVIDIA-SMI 550.107.02             Driver Version: 550.107.02     CUDA Version: 12.4`  

2.  
sanity check gpu info:  
`lspci | grep -i nvidia`  
> `01:00.0 3D controller: NVIDIA Corporation GP107M [GeForce GTX 1050 Ti Mobile] (rev a1)`  

3.  
using miniconda to more easily and flexibly manage cuda and cudnn:  
- download  
`pushd ~`
`curl -O https://repo.anaconda.com/archive/Miniconda3-latest-Linux-x86_64.sh`  
- install  
`curl -O https://repo.anaconda.com/archive/Anaconda3-<INSTALLER_VERSION>-Linux-x86_64.sh`  
- manually accept license, etc  
- restart  
`source ~/.bashrc`  


