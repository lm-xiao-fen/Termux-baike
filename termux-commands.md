# Termux 常用指令指南

*作者：lm-xiao-fen*  
*最后更新：2025-05-24 04:44:14 UTC*

## 目录
- [基本系统操作](#基本系统操作)
- [文件和目录操作](#文件和目录操作)
- [文件内容操作](#文件内容操作)
- [系统信息](#系统信息)
- [网络相关](#网络相关)
- [权限管理](#权限管理)
- [终端操作](#终端操作)
- [压缩和解压](#压缩和解压)

## 基本系统操作

```bash
pkg update             # 更新包列表
pkg upgrade           # 升级已安装的包
pkg install <包名>    # 安装新的包
pkg uninstall <包名>  # 卸载包
```

## 文件和目录操作

```bash
ls                    # 列出当前目录的文件
cd <目录>            # 切换目录
pwd                   # 显示当前目录路径
mkdir <目录名>       # 创建新目录
rm <文件名>          # 删除文件
rm -r <目录名>       # 删除目录
cp <源文件> <目标文件>   # 复制文件
mv <源文件> <目标文件>   # 移动/重命名文件
```

## 文件内容操作

```bash
cat <文件名>         # 查看文件内容
nano <文件名>        # 使用nano编辑器编辑文件
vim <文件名>         # 使用vim编辑器编辑文件（需要先安装）
```

## 系统信息

```bash
uname -a             # 显示系统信息
df -h                # 显示存储空间使用情况
top                  # 显示进程信息
ps                   # 显示当前进程
```

## 网络相关

```bash
ping <地址>          # 测试网络连接
wget <URL>           # 下载文件
curl <URL>           # 获取网页内容
```

## 权限管理

```bash
chmod +x <文件名>    # 添加执行权限
chmod 777 <文件名>   # 给予所有权限
```

## 终端操作

```bash
clear                # 清屏
exit                 # 退出终端
history              # 显示命令历史
```

## 压缩和解压

```bash
tar -zxvf <文件名.tar.gz>  # 解压tar.gz文件
tar -jxvf <文件名.tar.bz2> # 解压tar.bz2文件
unzip <文件名.zip>         # 解压zip文件
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
   ```

4. 使用 `man <命令>` 可以查看命令的详细说明（需要先安装 man 包）

 许可证
 
 MIT LICENSE
