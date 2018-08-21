# Install-TF_GPU-Keras-without-installing-CUDA-KIT
Installing Tensorflow GPU and Keras on GTX 1070 without installing CUDA 9.0 on Windows 10

Tensorflow requires CUDA DLL's and we can use tensorflow GPU without installing full package of NVidia CUDA 9.0
On new Nvidia GPU's and with latest Nvidia drivers, we face errors during installation and also an message during system check that Nvidia CUDA 9.0 is not compatible with hardware and may not work.

Steps I done : 
1. Install Visual Studio 2017 community edition and added cmake package while installing.
2. Install CUDA 9.2 development Kit
3. Install CUDnn library
4. Install Anaconda

Since tensorflow requires CUDA 9.0, so installing only runtime libraries is sufficient for tensorflow to run properly.
1. Create a new folder inside C directory
in my case : C:\Users\GJ\lib\CUDA9.0
2. Install CUDA 9.0 runtime libraries alone using custom installation and refer to this path for installation. this will create the bin directory inside the CUDA9.0 folder.
3. Install the CUDnn library
4. Update User Environment variable to add this path (C:\Users\GJ\lib\CUDA9.0\bin) to the environment variable.

After installing Anaconda, created a new environment using below command :
1. conda create --name kerasgpu --clone root ####--clone will copy all the packages from base
2. conda install -c aaronzs tensorflow-gpu
3. conda install -c anaconda keras-gpu

References : https://www.pugetsystems.com/labs/hpc/Install-TensorFlow-with-GPU-Suppor7t-on-Windows-10-without-a-full-CUDA-install-1172/

Copy the code from below link to compare the performance between tensorflow cpu and gpu : 
https://colab.research.google.com/notebooks/gpu.ipynb
