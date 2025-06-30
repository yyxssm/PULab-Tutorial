# 复旦PU Lab 实验室文档




## 目录

- [复旦PU Lab 实验室文档](#复旦pu-lab-实验室文档)
  - [如何做科研](#如何做科研)
  - [开心一刻](#开心一刻)
  - [PU Lab V100 服务器账号申请](#pu-lab-v100-服务器账号申请)
  - [3080Ti 或 3090 工作站使用](#3080ti-或-3090-工作站使用)
    - [推荐软件](#推荐软件)
    - [工作站使用规范](#工作站使用规范)
  - [Docker 使用教程](#docker-使用教程)
    - [1. 什么是 Docker？](#1-什么是-docker)
    - [2. Docker 基本命令](#2-docker-基本命令)
    - [3. 如何打包一个docker镜像](#3-如何打包一个docker镜像)
  - [学术会议出国申请流程](#学术会议出国申请流程)


## 更新日志
- 2025.06.29：更新《学术会议出国申请流程》
- 2025.01.05：更新《如何做科研》板块中的“过拟合实验”、“如何在组会汇报工作进展”。新增《开心一刻》板块。
- 2025.01.09：更新《如何做科研》板块中的“实用工具推荐”


## 如何做科研

* **学习别人的经验**：建议参考浙大一位老师的[科研经验分享](https://github.com/pengsida/learning_research)
  * 建议在不同的科研阶段侧重方面的内容，例如在科研初期，着重阅读 [如何培养科研能力](https://github.com/pengsida/learning_research/blob/master/getting_advanced_in_research.md)、[如何做research project](https://pengsida.notion.site/research-project-b43507ef26d044bd888ac29f4736e116)
  * 在实验阶段，着重阅读 [如何分析实验不work原因](https://pengsida.notion.site/work-1aee6e718de6472f834d13da8f4ff097)、[如何做实验记录](https://pengsida.notion.site/caf34717f4c046c69ee7e14ea953c46f)、[如何与同门、导师汇报](https://pengsida.notion.site/d697ef578d784c869d4f8314f0d617da)
  * 在实验后期和论文写作阶段，着重阅读 [如何写论文](https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e)。**需要注意实验和论文不应该是独立的两部分！**两者应该是紧密关联在一起，论文中如何讲故事与模型method相辅相成

* **扩大知识面**：
  * 关注一些科技类公众号（如：机器之心、新智元、量子位、Founder Park）
  * 关注一些科技类博客（手机下载小宇宙软件，关注 硅谷101、大小马聊科技、声动早咖啡）

* **过拟合实验**
  * 在进行全数据集实验前，必须先做过拟合实验！**不做过拟合实验直接用大数据集做实验的话，请全组人喝奶茶！**
  * [什么是过拟合实验](overfit.md)

* **如何在组会汇报工作进展**
  * 强烈建议所有同学认真读这一篇文章[《如何与同门、导师汇报》](https://pengsida.notion.site/d697ef578d784c869d4f8314f0d617da)
  * 第一次在组会上汇报自己工作时，需要把任务背景、意义、related works、自己的motivation说清楚
    * 错误范例：第一次汇报时，直接上来讲模型结构，别人根本不知道你要做什么任务
  * 后续在组会上汇报时，严禁重复性地介绍研究背景，直接切入重点，讲自己的方法和实验结果。**（再次强调要有过拟合实验的结果）**
  * 对于实验结果，要有自己的分析。如果实验效果变好了，是为什么变好了？如果实验效果不好，又是哪些地方可能出现问题？后续怎么做？
    * 错误范例：在实验分析部分，PPT上放了几张可视化，没有自己的思考分析，就只说：“这是可视化，大家看一下”。
  * 每次汇报时，都需要把PPT和实验打磨到自己认为完美的程度。只有这样，当别人指出问题时，你才能真正有所提升。如果PPT随便做、随便讲，实验也漏洞百出，别人不仅听不懂你在说什么，你自己也得不到任何成长，最终浪费的是双方的时间。

* 实用工具推荐
  * 论文管理工具：Zotero
  * AI查询工具（可用于搜索论文、背景调研）：
    * https://www.perplexity.ai/ (需要用英语搜索)
    * https://metaso.cn
    * https://flowith.io/conv/fce956df-e1eb-4abf-a667-77f685dcad0e
    * https://bohrium.dp.tech/home

## 开心一刻
  为了增加阅读的趣味性，特设“开心一刻”板块，列举一些新入学同学容易犯的典型问题，寓教于乐。

  * 每次汇报都介绍一次相同研究背景，完全是浪费时间，我倾向于认为你什么工作都没做，讲研究背景是用来凑时间的
    <details>
    <summary><b>《一遍还是两遍》</b></summary>

    实验室组会上，小李每次汇报都花5分钟讲一模一样的研究背景。导师终于忍不住了，说：“小李，以后直接讲你的工作进度，别浪费时间。”

    小李点点头，说：“好的，导师。我的工作进度是……没有实验。”

    导师愣了一下：“然后呢？”

    小李微微一笑：“然后我的汇报结束了。”

    导师无奈地叹了口气：“你这5分钟的背景介绍，原来是为了掩盖你这5秒钟的汇报啊！”

    导师扶额：“下次你再这样，我就让你讲10分钟的背景，看你还能不能凑出10秒钟的汇报！”

    小李想了想，认真地说：“那我可以把背景讲两遍。”

    导师：“……”
    </details>


  * 论文调研要充分，多用各种关键词组合搜索
    <details>
    <summary><b>《怀旧式科研》</b></summary>

    在一次组会上，小严汇报完自己的工作后，导师问：“这个任务上别人有什么方法？他们的方法存在哪些问题？”

    小严支支吾吾，一问三不知。

    导师叹了口气：“调研都没调研清楚，怎么做科研？要是闭门造车，你做的东西后来发现别人十年前就做过了，岂不是白忙活了？”

    小严挠挠头，小声嘀咕：“那至少证明我的思路是对的……只是晚了十年。”

    导师扶额：“那你干脆再等二十年，说不定还能赶上别人二十年前的工作。”

    小严眼睛一亮：“导师，您是说……我这是‘复古科研’，走的是怀旧路线？”

    导师：“……”
    </details>


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

**注意这里命名的时候也要注意加上姓名缩写！**

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

# 学术会议出国申请流程
（初版，待完善）

**注意：1）所有的酒店、机票、会议注册费都要自己保存好发票，飞机还需要开行程单。2）飞机的出发到达都是上海，行程单上需要标注是经济舱。3）发票都是复旦的抬头** 


1. 首先你需要有护照，没有护照的先去办护照，护照有效期至少要大于会议结束日期6个月，否则无法申请签证
2. 自己做一个[行程规划](会议行程规划.pdf)，自己规划一下几号出发 几号回国、住什么酒店、飞机票多少钱、酒店多少钱。需要是给几套方案，然后让老师来选。
    * 机票在航旅纵横上订，比较便宜。不要去其他软件订票，这个软件是浦老师严选，在航旅纵横上订贵了，是软件的问题，在其他软件上订贵了，就是你的问题。
    * 住宿需要去参照[学校的报销额度](https://fao.fudan.edu.cn/cyxx/list.htm)，不要超支了。
    * 不要觉得能报销就专挑贵的选，可能老师看太贵了，就不让去参会了。
3. 在会议官网注册账号，交掉注册费（交钱前先和浦老师确认好），申请好邀请信（invitation letter）
4. ehall上搜索“全日制在读学生因公出国（境）审批”，同时自己去申请办理签证（理论上是申请商务签）
    * 注意: ehall申请的第一步需要学院审批，还需要将[类脑研究院学生出国（出境）登记表](类脑研究院学生出国（出境）登记表.docx)在网申中作为附件上传，这个文件在ehall上没有，放在github里了，自己下载
    * 还有一个学校的会议资助可以申请：[关于开展研究生国际学术会议资助项目申报工作的通知](https://gs.fudan.edu.cn/32/fc/c2891a668412/page.htm)
5. 等学校审批通过、签证下来后，抓紧时间订机票和酒店，越晚订越贵。
