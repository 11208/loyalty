python convert.py model_data/loyalty.cfg model_data/yolov3.weights model_data/loyalty.h5

Install Nvidia driver::
sudo apt-get install ubuntu-drivers-common -y
sudo ubuntu-drivers devices
sudo ubuntu-drivers autoinstall
sudo shutdown -r now
sudo lshw -c display
nvidia-smi

Install Nvidia CUDA::
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-ubuntu1804.pin
sudo mv cuda-ubuntu1804.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget http://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda-repo-ubuntu1804-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1804-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo apt-key add /var/cuda-repo-10-1-local-10.1.243-418.87.00/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda


Installation of Deep Neural Network library (cuDNN)::
download: https://developer.nvidia.com/rdp/cudnn-archive
scp .\libcudnn7-dev_7.5.0.56-1+cuda10.1_amd64.deb innovation@192.168.1.55:/home/innovation/cudnn7_dev.deb
scp .\libcudnn7_7.5.0.56-1+cuda10.1_amd64.deb innovation@192.168.1.55:/home/innovation/cudnn7.deb
sudo dpkg -i cudnn7*.deb

Install pip3::
sudo apt install python3-pip -y

wget https://pjreddie.com/media/files/darknet53.conv.74


sudo ./darknet detector calc_anchors cfg/oishi.data -num_of_clusters 9 -width 416 -height 416 -show
sudo cp oishi_7000.weights ~/deep-redeem/modules/darknet/cfg/oishi.weights

CMD: sudo ./darknet detector map cfg/oishi.data cfg/oishi.cfg backup/oishi_10000.weights

