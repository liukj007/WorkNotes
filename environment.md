# 服务器环境配置
---
## Anaconda
---
### 下载Anaconda
进入[Anaconda官网](https://www.anaconda.com/)下载所需脚本，例如*Anaconda3-2024.02-1-Linux-x86_64.sh*。

### 安装Anaconda
1.脚本命令安装  
```
bash /xxx/Anaconda3-2023.01-Linux-x86_64.sh
```
2.一直按回车，或按q+yes跳过阅读  
(1)默认安装在用户目录下，回车即可安装；  
(2)也可自定义安装目录，直接输入安装目录，回车即可安装；  
(3)直到出现“Do you wish the installer to initialize Anaconda3 by running conda init ? ”，输入no，回车。  
ps：官方建议yes，直接初始化，但选择yes后会导致无法使用conda命令，依然需要添加环境变量，添加后正常使用。

### 配置环境变量

1.输入`conda`，如果出现`conda: command not found`则说明未添加环境变量  

2.向系统环境变量中添加Anaconda路径  
(1)首先执行vim打开.bashrc：  
```
vim ~/.bashrc
```
(2)然后按a或i进行编辑（注意只能利用光标移动，鼠标移动无效），添加环境变量：  
```
export PATH=$PATH:/xxx/xxx/anaconda3/bin
```
(3)然后按Esc键推出编辑，输入`:wq!`进行保存并推出，激活刚刚更新的bashrc:  
```
source ~/.bashrc
```
3.在此输入`conda`，显示具体信息后即为成功。

## base_env创建
---
### 创建虚拟环境
```
conda create -n base_env python=3.8
```
### Pytorch安装
激活虚拟环境  
```
conda activate base_env
```
因为此前未运行conda init，可能报错`CondaError: Run 'conda init' before 'conda activate'`,运行`conda init`然后重启terminal即可激活虚拟环境  
进入[Pytorch官网](https://pytorch.org/)，根据CUDA选择安装,4卡A100`CUDA Version = 11.7`，Pytorch尽量选择高版本，因为其向下兼容，CUDA尽量匹配，也可小于自己的版本  
```
conda install pytorch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 pytorch-cuda=11.7 -c pytorch -c nvidia
```
命令行输入`python`，可进入编程界面，`quit()`退出，输入以下代码进行验证  
```
import torch  
torch.cuda.is_available()
```
查看torch版本  
```
torch.__version__
```
## 新建虚拟环境
已搭建基础环境 `base_env (python 3.8 + pytorch 2.0.1)`  
如果需要新建虚拟环境，可以在上述基础环境上搭建
```
conda create -n <custom_env_name> --clone base_env
```
## 其他包安装
```
pip install name
pip install name=xxx
pip install name -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
pip install name -i https://pypi.tuna.tsinghua.edu.cn/simple --trusted-host pypi.tuna.tsinghua.edu.cn
```