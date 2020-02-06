# gpu-cuda-installation
This repo has steps for installing gpu drivers (CUDA)

1. `sudo apt update`
2. `sudo add-apt-repository ppa:graphics-drivers/ppa`
3. `sudo apt-key adv --fetch-keys  http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub`

4. `sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64 /" > /etc/apt/sources.list.d/cuda.list'`

5. `sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64 /" > /etc/apt/sources.list.d/cuda_learn.list'`

6. `sudo apt update`
7. `sudo apt install cuda-10-1`
8. `sudo apt install libcudnn7`

9. `sudo vi ~/.profile`

10. Add to the end of file:
```
# GPU
if [ -d "/usr/local/cuda-10.1/bin/" ]; then
    export PATH=/usr/local/cuda-10.1/bin${PATH:+:${PATH}}
    export LD_LIBRARY_PATH=/usr/local/cuda-10.1/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
fi
```
10.1 press (editing): ctrl+I
10.2 press (insert text above): ctrl+v
10.3 press (write changes): ctrl+w
10.4 press (exit): ctrl+x

11. ```sudo reboot```
12. ```nvidia-smi```
13. ```sudo apt purge nvidia-*```
14. ```sudo add-apt-repository ppa:graphics-drivers/ppa```
15. ```sudo apt update```
16. ```sudo apt install nvidia-381```

You can use system pip:

17. ```sudo pip3.7 install torch torchvision```

but we think this is bad idea. We think you need to use anaconda. Than install anaconda and create env:

18. ```conda create --name torch python=3.7```
19. ```conda activate torch```
20. ```pip install torch torchvision```

Thanks for instruction [Petr Kozyrev](https://github.com/Humboldt155)

