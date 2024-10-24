@[TOC](环境配置final版本)

# step1: 安装conda
conda要根据服务器来选择，比如服务器是linux x86_64的，就选择对应的conda。以miniconda为例：
```shell
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
```
然后就可以安装conda了, 安装完毕之后激活base环境。
# step2: 创建环境
以环境名为livedraft为例，选择python版本为3.10：
```bash
conda create -n livedraft python=3.10
conda activate livedraft
```
# step3: 安装torch
安装torch的时候要根据服务器的cuda的版本，去官网上选择合适的torch版本，然后选择合适的命令安装。服务器没有GPU就选择CPU only的命令
```bash
conda install pytorch==2.3.0 torchvision==0.18.0 torchaudio==2.3.0 cpuonly -c pytorch
```
# step4: centos系统
贵公司的服务器是centos系统，因此需要一些注意事项：
```bash
# 1.安装gcc和g++   
yum -y install gcc gcc-c++ kernel-devel
#2. Cython版本小于3.0.0  
pip install --upgrade Cython==0.29.35
# 3.numpy版本小于2.0   
pip install numpy==1.26.0
```
# step5: 安装音频模型库
```bash
pip install "modelscope[audio]" -f https://modelscope.oss-cn-beijing.aliyuncs.com/releases/repo.html
```
# step6: 安装项目依赖
```bash
pip install -r requirements.txt
```
