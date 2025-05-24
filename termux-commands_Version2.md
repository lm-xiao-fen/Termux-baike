# Termux 常用指令指南(补）

*作者：lm-xiao-fen*  
*最后更新：2025-05-24 08:39:52 UTC*

## 目录
- [基本系统操作](#基本系统操作)
- [文件和目录操作](#文件和目录操作)
- [文件内容操作](#文件内容操作)
- [系统信息](#系统信息)
- [网络相关](#网络相关)
- [权限管理](#权限管理)
- [终端操作](#终端操作)
- [压缩和解压](#压缩和解压)
- [进阶操作](#进阶操作)
- [包管理进阶](#包管理进阶)
- [存储访问](#存储访问)
- [SSH 操作](#ssh-操作)
- [常用开发环境配置](#常用开发环境配置)

## 基本系统操作

```bash
pkg list-installed    # 列出已安装的包
pkg search <关键词>   # 搜索可用的包
```

## 文件和目录操作

```bash
ls -la               # 列出详细信息，包括隐藏文件
mkdir -p <路径>      # 创建多级目录
rm -rf <目录名>      # 强制删除目录及其内容
cp -r <源目录> <目标目录> # 复制目录
touch <文件名>       # 创建空文件
```

## 文件内容操作

```bash
head <文件名>        # 查看文件开头部分
tail <文件名>        # 查看文件结尾部分
tail -f <文件名>     # 实时查看文件更新
grep <pattern> <文件名> # 搜索文件内容
less <文件名>        # 分页查看文件内容
```

## 系统信息

```bash
ps aux              # 显示所有进程详细信息
free                # 显示内存使用情况
neofetch            # 显示系统信息（需要安装）
htop                # 交互式进程查看器（需要安装）
```

## 网络相关

```bash
ifconfig            # 显示网络接口信息（需要安装net-tools）
ip addr             # 显示IP地址信息
ssh <用户名>@<主机> # SSH连接（需要安装openssh）
scp <源文件> <目标>  # 远程复制文件（需要安装openssh）
netstat             # 显示网络状态（需要安装net-tools）
```

## 权限管理

```bash
chmod -R 755 <目录>  # 递归修改目录权限
chown <用户> <文件>  # 修改文件所有者
```

## 终端操作

```bash
reset               # 重置终端
ctrl + c            # 中断当前程序
ctrl + z            # 挂起当前程序
fg                  # 将后台程序调至前台
bg                  # 将程序放到后台运行
```

## 压缩和解压

```bash
tar -zcvf <文件名.tar.gz> <目录> # 压缩目录为tar.gz
tar -jcvf <文件名.tar.bz2> <目录> # 压缩目录为tar.bz2
zip -r <文件名.zip> <目录> # 压缩目录为zip文件
```

## 进阶操作

```bash
screen              # 终端复用（需要安装）
tmux                # 终端复用（需要安装）
nmap                # 网络扫描（需要安装）
git                 # 版本控制（需要安装）
python              # Python解释器（需要安装）
gcc                 # C/C++编译器（需要安装）
```

## 包管理进阶

```bash
apt update          # 更新包索引
apt upgrade         # 升级包
apt list           # 列出可用包
apt show <包名>    # 显示包信息
apt install -y     # 自动确认安装
apt clean          # 清理安装包缓存
```

## 存储访问

```bash
termux-setup-storage  # 请求存储权限
cd ~/storage          # 进入存储目录
cd ~/storage/dcim    # 进入相机目录
cd ~/storage/downloads # 进入下载目录
cd ~/storage/pictures # 进入图片目录
```

## SSH 操作

```bash
ssh-keygen          # 生成SSH密钥对
ssh-copy-id user@host # 复制SSH公钥到远程主机
sshd                # 启动SSH服务器
pkill sshd          # 停止SSH服务器
```

## 常用开发环境配置

1. Python开发环境：
```bash
pkg install python
pip install --upgrade pip
```

2. Node.js开发环境：
```bash
pkg install nodejs
npm install -g npm
```

3. Git配置：
```bash
pkg install git
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## 重要提示

1. 在使用Termux之前，建议首先运行以下命令以确保系统是最新的：
   ```bash
   pkg update && pkg upgrade
   ```

2. 一些命令可能需要先安装相应的包才能使用

3. 使用以下命令安装常用工具：
   ```bash
   pkg install vim    # 安装vim编辑器
   pkg install man    # 安装man手册
   pkg install wget   # 安装wget下载工具
   pkg install curl   # 安装curl工具
   pkg install git    # 安装git版本控制
   pkg install openssh # 安装SSH工具
   ```

4. 使用 `man <命令>` 可以查看命令的详细说明（需要先安装 man 包）

5. Termux快捷键：
   - 音量加号+Q：显示额外按键行
   - 音量加号+W：向上翻页
   - 音量加号+S：向下翻页
   - 音量加号+A：将光标移到行首
   - 音量加号+D：将光标移到行尾

6. 定制化：
   - 编辑 `~/.termux/termux.properties` 自定义终端外观
   - 编辑 `~/.bashrc` 设置环境变量和别名

## 许可证
MIT LICENSE
