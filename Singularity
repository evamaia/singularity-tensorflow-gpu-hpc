Bootstrap: docker
From: ubuntu:18.04

%environment
    SHELL=/bin/bash
    export SHELL

%files
    tensorflow_demo.py 


%post
    apt -y update
    apt -y install wget
    apt -y install gnupg
    apt -y install gnupg1
    apt -y install gnupg2



    apt -y install python3
    apt -y install python3-pip
    

    
    # Add NVIDIA package repository
    apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
    wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
    apt -y install ./cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
    wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1604/x86_64/nvidia-machine-learning-repo-ubuntu1604_1.0.0-1_amd64.deb
    apt -y install ./nvidia-machine-learning-repo-ubuntu1604_1.0.0-1_amd64.deb
    apt -y update

    # Install CUDA and tools. Include optional NCCL 2.x
    apt -y install cuda9.0 cuda-cublas-9-0 cuda-cufft-9-0 cuda-curand-9-0 \
        cuda-cusolver-9-0 cuda-cusparse-9-0 libcudnn7=7.2.1.38-1+cuda9.0 \
        libnccl2=2.2.13-1+cuda9.0 cuda-command-line-tools-9-0

    # Optional: Install the TensorRT runtime (must be after CUDA install)
    apt -y update
    apt -y install libnvinfer4=4.1.2-1+cuda9.0

    pip3 install tensorflow-gpu
    pip3 install pandas
    pip3 install matplotlib
    pip3 install keras
    pip3 install numpy
    pip3 install pillow


