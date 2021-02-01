# 安装cuda和cudnn：
版本要求：cuda-10.2，cudnn8
## 1.安装cuda-10.2：
（1）下载地址：
https://developer.nvidia.com/cuda-10.2-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=runfilelocal

（2）安装指令：
```
sudo sh cuda_<version>.run  //在安装界面中取消驱动下载
```
（3）环境配置：
```
sudo vim ~/.bashrc
末尾添加
export PATH=/usr/local/cuda-10.1/bin:/usr/local/cuda-10.2/NsightCompute-2019.5.0${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-10.2/lib64\
                         ${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
保存，执行如下命令使得配置生效
source ~/.bashrc
```
## 2.安装cudnn8：
（1）下载地址：
https://developer.nvidia.com/rdp/cudnn-download

 (2) 配置cudnn：
```
sudo cp cuda/include/* /usr/local/cuda-10.2/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda-10.2/lib64
sudo chmod a+r /usr/local/cuda-10.2/include/cudnn.h 
sudo chmod a+r /usr/local/cuda-10.2/lib64/libcudnn*
```
# 安装opencv4.2
(1) 下载地址：
https://github.com/opencv/opencv/releases/tag/4.2.0

(2) 安装：
```
依赖包：
sudo apt-get install cmake libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff5-dev libdc1394-22-dev  # 处理图像所需的包
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev liblapacke-dev
sudo apt-get install libxvidcore-dev libx264-dev      # 处理视频所需的包
sudo apt-get install ffmpeg
```
```
进入opencv源码目录，创建build 目录,cd build 运行
cmake -D CMAKE_BUILD_TYPE=Release -D OPENCV_GENERATE_PKGCONFIG=YES -D CMAKE_INSTALL_PREFIX=/usr/local  -D WITH_GTK=ON 

make -j4

sudo make install
```

# 安装openvino：
解压openvino压缩包后运行simple_install.sh一键安装脚本。
# 安装TensorRT：
## 安装TensorRT SDK 7.1
（1）下载路径：
https://developer.nvidia.com/nvidia-tensorrt-7x-download

（2）安装
```
tar -xvzf TensorRT-7.1.3.4.Ubuntu-18.04.x86_64-gnu.cuda-10.2.cudnn8.0.tar.gz
```
