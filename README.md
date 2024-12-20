# 复旦PU Lab 实验室文档




## 目录

- [复旦PU Lab 实验室文档](#复旦pu-lab-实验室文档)
  - [如何做科研](#如何做科研)
  - [PU Lab V100 服务器账号申请](#pu-lab-v100-服务器账号申请)
  - [3080Ti 或 3090 工作站使用](#3080ti-或-3090-工作站使用)
    - [推荐软件](#推荐软件)
    - [工作站使用规范](#工作站使用规范)
  - [Docker 使用教程](#docker-使用教程)
    - [1. 什么是 Docker？](#1-什么是-docker)
    - [2. Docker 基本命令](#2-docker-基本命令)
    - [3. 如何打包一个 Docker 镜像](#3-如何打包一个-docker-镜像)



## 如何做科研

* **学习别人的经验**：建议参考浙大一位老师的[科研经验分享](https://github.com/pengsida/learning_research)
  * 建议在不同的科研阶段侧重方面的内容，例如在科研初期，着重阅读 [如何培养科研能力](https://github.com/pengsida/learning_research/blob/master/getting_advanced_in_research.md)、[如何做research project](https://pengsida.notion.site/research-project-b43507ef26d044bd888ac29f4736e116)
  * 在实验阶段，着重阅读 [如何分析实验不work原因](https://pengsida.notion.site/work-1aee6e718de6472f834d13da8f4ff097)、[如何做实验记录](https://pengsida.notion.site/caf34717f4c046c69ee7e14ea953c46f)、[如何与同门、导师汇报](https://pengsida.notion.site/d697ef578d784c869d4f8314f0d617da)
  * 在实验后期和论文写作阶段，着重阅读 [如何写论文](https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e)。**需要注意实验和论文不应该是独立的两部分！**两者应该是紧密关联在一起，论文中如何讲故事与模型method相辅相成

* **扩大知识面**：
  * 关注一些科技类公众号（如：机器之心、自动驾驶之心、量子位、具身智能之心、Founder Park）
  * 关注一些科技类博客（手机下载小宇宙软件，关注 硅谷101、大小马聊科技、声动早咖啡）


## PU Lab V100 服务器账号申请

1. 请参考这个 [链接](https://10.190.248.224/books/bd686/page/d67d8) 申请账号。注意：该链接中的申请邮箱有误，请将邮件发送给戴飞老师（fdai@fudan.edu.cn）。
2. 申请账号后，需要联系戴飞老师（fdai@fudan.edu.cn），请求开通访问 V100 的权限，并加入 PULab 的 group，否则无法访问共享数据集。

## 3080Ti 或 3090 工作站使用

由于工作站是分配到小组的，SSH 账号密码需要向自己科研组的师兄师姐索取。

### 推荐软件

为提高使用效率，推荐以下软件：

- **编程 IDE**：建议使用 VSCode 或 PyCharm（注意 PyCharm 专业版需要学生验证可免费使用，详情请访问官网）。
- **图形化 SSH 链接软件**：建议使用 MobaXterm。

请提前安装以上软件，如遇到问题可在组内交流。

此外，为了在关闭访问进程后不中断训练，推荐使用进程管理工具 Tmux，参考 [教程链接](https://blog.csdn.net/Aibiabcheng/article/details/122482786)。

### 工作站使用规范

由于工作站系统盘空间有限，**安装 conda 虚拟环境时严禁装到系统盘中！**

由于多人合用同一个工作站，安装虚拟环境时，**如果需要用到`python setup.py develop`命令，严禁使用`--user`后缀！**即只能使用`python setup.py develop`安装环境，不能使用`python setup.py develop --user`



请使用以下命令安装虚拟环境，使用 `-p` 参数指定安装位置，将虚拟环境安装到其他磁盘：

```bash
conda create -p 安装路径
```

例如：将环境安装到/home3下名为yyx的个人文件夹中

```bash
conda create -p /home3/yyx/anaconda3/envs/myenv python=3.8 -y
```


## Docker 使用教程 

### 1. 什么是 Docker？ 

Docker 是一种开源的容器化平台，用于开发、发布和运行应用。它可以在轻量的容器中打包应用及其依赖项，确保在不同环境中一致运行。

### 2. Docker 基本命令

#### 2.1 启动和停止 Docker

```bash
# 启动 Docker
sudo systemctl start docker

# 停止 Docker
sudo systemctl stop docker
```

#### 2.2 查看 Docker 版本

```bash
docker --version
```

#### 2.3 拉取镜像

```bash
# 拉取指定镜像
docker pull <镜像名称>:<标签>

# 例如，拉取最新的 Ubuntu 镜像
docker pull ubuntu:latest
```

#### 2.4 列出镜像

```bash
docker images
```

#### 2.5 运行容器

```bash
# 以交互方式启动容器
docker run -it <镜像名称> /bin/bash

# 例如，运行一个 Ubuntu 容器
docker run -it ubuntu /bin/bash
```

#### 2.6 查看容器

```bash
# 查看运行中的容器
docker ps

# 列出本机的所有容器
docker ps -a
```

#### 2.7 停止容器

```bash
docker stop <容器ID或名称>
```

#### 2.8 删除容器

```bash
docker rm <容器ID或名称>
```

#### 2.9 删除镜像

```bash
docker rmi <镜像ID或名称>
```

### 3. 如何打包一个docker镜像

本教程将介绍如何使用 `continuumio/anaconda3` 镜像创建一个 Docker 容器，将所需的环境和代码复制到容器中，然后将容器上传到蘑菇服务器。

<p style="color:red; display:inline;"><strong>注意！</strong></p> docker容器命名规范：`自己名字的缩写（姓全拼+名简写）_容器名`，例如：张三想创建一个名为test的容器，则容器名为`zhangs_test`

<p style="color:red; display:inline;"><strong>注意！</strong></p> 由于工作站上存储空间有限，如果某个docker容器或docker镜像无需使用，请立刻删除！严禁保存过多镜像



#### 1. 拉取基础镜像

 首先，我们需要拉取 `continuumio/anaconda3` 镜像。

 ```bash 
docker pull continuumio/anaconda3
 ```

#### 2. 创建容器

（**不推荐此方法**，docker内部不可见nvidia-smi）用拉取的 `continuumio/anaconda3` 镜像创建一个名为 `zs_test ` 的容器。

```bash
docker run --name zhangs_test -idt continuumio/anaconda3
```

**（推荐）**如果需要在容器中使用 GPU，可以通过以下命令让容器可见 `nvidia-smi`

```bash
docker run -itd --gpus all --name 容器名 -e NVIDIA_DRIVER_CAPABILITIES=compute,utility -e NVIDIA_VISIBLE_DEVICES=all 镜像名

# 示例：
docker run -itd --gpus all --name zhangs_test -e NVIDIA_DRIVER_CAPABILITIES=compute,utility -e NVIDIA_VISIBLE_DEVICES=all continuumio/anaconda3
```

#### 3. 进入容器

进入容器以检查 Anaconda 的位置。

```bash
docker exec -it zhangs_test /bin/bash
```

在容器内，使用以下命令查看 Anaconda 的位置：

```bash
conda env list
# 或使用
conda info --envs
```

查看完后，可以通过快捷键退出容器：

- **退出快捷键**：`Ctrl + D`

#### 4. 将本地环境复制到 Docker 容器中

退出容器后，使用以下命令将需要打包的本地环境复制到 Docker 容器中。例如，将本地的 Conda 环境 `/home/b/miniconda3/envs/yolo1.7` 复制到容器的 `/opt/conda/envs` 路径下（通过 `conda info --envs` 获取容器内的环境路径）。

```bash
docker cp /home/b/miniconda3/envs/yolo1.7 zhangs_test:/opt/conda/envs
```

------

#### 5. 检查环境是否复制成功

再次进入容器，检查环境是否已复制成功。

```bash
docker exec -it zhangs_test /bin/bash

conda env list
```

#### 6. 在容器内安装必要的包

```bash
apt-get update
apt-get install vim
apt-get install unzip
apt-get install zip
apt-get install tmux
pip install nvitop
apt-get install git
# ========== 配置你的git，改成你自己的 ============
config --global user.name 'zhangs'
config --global user.email 'zhangs@163.com'
# ==============================================
apt-get install ninja-build
apt install libxml2

# 安装open3d依赖库
apt install libgl1-mesa-glx
apt-get install libgomp1

# 安装ping
apt install iputils-ping
apt install net-tools

# 配置coscmd
pip install coscmd
# 这里还需要配置coscmd的账号密码，为保密起见，不上传至github

# 安装cuda
apt update
apt -y install libxml2
apt-get install make gcc g++ 
apt-get install manpages-dev

# ========== 如果是安装cuda11.3 ==========
# 先ctrl+d退出容器
docker cp /home/csstuer/Downloads/cuda_11.3.0_465.19.01_linux.run zhangs_test:/
# 再进入容器，运行安装程序
# 注意！不要安装nvidia driver，否则会报错
sh cuda_11.3.0_465.19.01_linux.run

export CUDA_HOME=/usr/local/cuda-11.3
export PATH=$CUDA_HOME/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=$CUDA_HOME/lib64\${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
source ~/.bashrc
# =====================================


# ========= 如果是安装cuda11.1 ============
# 先ctrl+d退出容器
docker cp /home/csstuer/Downloads/cuda_11.1.1_455.32.00_linux.run zhangs_test:/
# 再进入容器，运行安装程序
# 注意！不要安装nvidia driver，否则会报错
sh cuda_11.1.1_455.32.00_linux.run
# 在~/.bashrc中配置
export CUDA_HOME=/usr/local/cuda-11.1
export PATH=$CUDA_HOME/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=$CUDA_HOME/lib64\${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
source ~/.bashrc
# =====================================
```

#### 7. 将容器保存为镜像

现在，`zhangs_test` 容器中已经包含我们所需的代码和环境，可以将其打包为镜像。

退出容器后，执行以下命令将容器保存为镜像：

```bash
docker commit -a 'author' -m 'instruction' 容器名称 保存的镜像名称

# 例如
docker commit -a 'zhangsan' -m 'docker for project zhangs_test' zhangs_test image_zhangs_test
```

#### 8. 镜像上传到蘑菇服务器

```bash
# 其中 [tag] 请根据您需要拉取镜像的具体版本镜像替换，如 latest。更多命令说明，请参看官方文档：docker pull

# 先打个标签
docker tag [imageId] mogohub.tencentcloudcr.com/tad-servers/tad:[tag]
# 向 Registry 中推送镜像
docker push mogohub.tencentcloudcr.com/tad-servers/tad:[tag]

# 例如
# 先打个标签
docker tag image_zhangs_test mogohub.tencentcloudcr.com/tad-servers/image_zhangs_test:v1.0
# 向 Registry 中推送镜像
docker push mogohub.tencentcloudcr.com/tad-servers/image_zhangs_test:v1.0
```

