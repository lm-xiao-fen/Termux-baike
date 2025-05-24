# Termux 软件源切换指南

*作者：lm-xiao-fen*
*更新时间：2025-05-24 10:30:48 UTC*

## 目录
- [自动切换方法](#自动切换方法)
- [手动切换方法](#手动切换方法)
- [推荐镜像源](#推荐镜像源)
- [常见问题解决](#常见问题解决)

## 自动切换方法

1. 使用 `termux-change-repo` 命令（推荐）：
```bash
# 安装 termux-tools（如果尚未安装）
pkg install termux-tools

# 运行切换软件源命令
termux-change-repo
```
按照交互式界面选择合适的镜像源即可。

## 手动切换方法

1. 备份原有的源文件：
```bash
cp $PREFIX/etc/apt/sources.list $PREFIX/etc/apt/sources.list.bak
```

2. 编辑源文件：
```bash
nano $PREFIX/etc/apt/sources.list
```

3. 替换内容为以下镜像源之一（选择一个即可）：

### 清华大学镜像源
```
deb https://mirrors.tuna.tsinghua.edu.cn/termux/apt/termux-main stable main
```

### 中科大镜像源
```
deb https://mirrors.ustc.edu.cn/termux/apt/termux-main stable main
```

### 阿里云镜像源
```
deb http://mirrors.aliyun.com/termux/termux-packages-24 stable main
```

4. 更新软件包索引：
```bash
pkg update
```

## 推荐镜像源

1. **国内镜像**（推荐）：
   - 清华大学镜像源：`https://mirrors.tuna.tsinghua.edu.cn/termux`
   - 中科大镜像源：`https://mirrors.ustc.edu.cn/termux`
   - 阿里云镜像源：`http://mirrors.aliyun.com/termux`

2. **官方镜像**：
   - 主源：`https://packages.termux.dev/apt/termux-main`

## 常见问题解决

1. **无法访问镜像源**
```bash
# 检查网络连接
ping mirrors.tuna.tsinghua.edu.cn

# 如果无法连接，尝试切换其他镜像源
```

2. **更新失败**
```bash
# 清理包缓存
pkg clean

# 强制更新
pkg update -y
```

3. **源文件损坏**
```bash
# 恢复备份的源文件
cp $PREFIX/etc/apt/sources.list.bak $PREFIX/etc/apt/sources.list

# 或重新安装 termux-tools
pkg install termux-tools
```

## 注意事项

1. 更换软件源后必须执行 `pkg update` 更新软件包索引

2. 如果遇到 SSL 证书问题，可以尝试：
```bash
termux-reset-ssl
```

3. 确保系统时间正确，否则可能导致 SSL 证书验证失败：
```bash
pkg install ntpupdate
ntpdate pool.ntp.org
```

4. 如果需要同时使用多个源，可以编辑 `sources.list` 添加多行配置

## 验证源是否生效

执行以下命令检查当前使用的软件源：
```bash
termux-info | grep MAIN
```

或查看源文件内容：
```bash
cat $PREFIX/etc/apt/sources.list
```

---
*提示：建议选择与您所在地理位置最近的镜像源以获得最佳下载速度。*