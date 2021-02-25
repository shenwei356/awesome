# Install CentOS

Taking centos 7 for example.

## Source

epel

    sudo yum install epel-release
    
elrepo: http://elrepo.org/tiki/HomePage

    yum install https://www.elrepo.org/elrepo-release-7.el7.elrepo.noarch.rpm

## Environment

    sudo yum groupinstall "Development Tools" 
  
selinux:     
    
- `vi /etc/sysconfig/selinux`,

        # SELINUX=enforcing
        SELINUX=disable
        
- 立即生效

        setenforce 0 
        
- 查看SELinux状态
    
        getenforce
        
python

    python3 -m pip install --upgrade pip
    
Add pip mirror

    pip install pip -U
    pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
    
## Disk

multipath

- https://blog.csdn.net/cxn888/article/details/105125366

    
## Network


防火墙

- https://cloud.tencent.com/developer/article/1633310
- https://www.freebuf.com/sectool/237569.html

ssh

- [Centos7修复ssh连接很慢的问题](https://www.jianshu.com/p/1966d2499d74)

vnc. [centos7下VNC黑屏解决办法](https://www.linuxstudy.cn/archives/67.html)

    sudo yum install -y tigervnc tigervnc-server
    
ssr

- https://github.com/shadowsocksrr/electron-ssr/releases 
- https://github.com/rofl0r/proxychains-ng 
- replace `/opt/electron-ssr/3rdparty/socks2http` https://github.com/xVanTuring/socks2http-rs 
        
        yum install rust cargo
        cargo build


## Utilities

sensors

    sudo yum install -y lm_sensors hddtemp
    sudo sensors-detect
    sensors
    
utilies

- bashmarks: https://github.com/huyng/bashmarks
- trash-cli: https://github.com/andreafrancia/trash-cli
- fd: https://github.com/sharkdp/fd
- rg: https://github.com/BurntSushi/ripgrep

Others

    sudo yum install -y pigz kate axel htop
    
## GPU

nvidia

- https://blog.csdn.net/qq_34666229/article/details/82184588
- https://blog.csdn.net/yinpizong5319/article/details/109106604

cuda

- 按官网教程来，下载再装rpm：https://developer.nvidia.com/CUDA-toolkit-archive 
- 官网 https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html
- [CentOS 7 安装CUDA 11.1 使用rpm包](https://blog.csdn.net/theITcat/article/details/109120083)

cudnn

- https://developer.nvidia.com/rdp/cudnn-download 

Tensorflow via conda

- https://docs.anaconda.com/anaconda/user-guide/tasks/tensorflow/, Use Nightly builds [RTX 3080 tensorflow实现Minist Demo](https://blog.csdn.net/m0_50480883/article/details/110267095)

        # check supported python first: https://pypi.org/project/tf-nightly-gpu/
        conda create -n tf-n-gpu python=3.8
        conda activate tf-n-gpu
        pip install tf-nightly-gpu -i https://mirrors.aliyun.com/pypi/simple

- missing libs

        sudo yum install -y cuda-cudart-11-1 \
            libcublas-11-1 libcublas-devel-11-1 \
            libcufft-11-1  libcufft-devel-11-1 \
            libcurand-11-1 libcurand-devel-11-1 \
            libcusolver-11-1 libcusolver-devel-11-1 \
            libcusparse-11-1 libcusparse-devel-11-1
        sudo yum install -y cuda-cusolver-10-2
        
        # and you may manually configure LD_LIBRARY_PATH to include libcusolver libs


- https://www.tensorflow.org/install/source?hl=zh-cn#gpu_support_3 


## Users

limit cores and memory

    echo "@xiaoming hard rss 2097152" >> /etc/security/limits.conf
    echo "#Sets up user limits according to /etc/security/limits.conf" >/etc/pam.d/login
    echo "session required pam_limits.so" > /etc/pam.d/login


