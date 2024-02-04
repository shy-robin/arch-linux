# Pacman 常用命令

## 常用命令

### 安装软件

`pacman -S` (-S for --sync)

### 更新软件源

`pacman -Sy` (-y 选项表示 --refresh，意味着刷新软件包数据库，以获取最新的软件包列表)

使用 `pacman -Sy` 命令时，pacman 将更新本地的软件包数据库，以确保它包含最新的软件包信息。这样，您就可以获得最新的可用软件包列表，并且在安装软件包之前，可以确保使用的是最新版本。

### 强制更新软件源

`pacman -Syy` (使用 pacman -Syy 命令时，pacman 将强制刷新本地的软件包数据库，即使已经是最新状态。这样做的目的是确保获取到最新的软件包列表。)

### 更新软件

`pacman -Su` (-S 选项表示 --sync，意味着使用同步数据库来安装/更新软件包。-u 选项表示 --sysupgrade，意味着升级系统中的所有软件包。)

使用 `pacman -Su` 命令时，pacman 将检查系统中已安装的软件包，并与软件仓库中的最新版本进行比较。如果有可用的更新版本，它将下载并安装这些更新，从而升级系统中的所有软件包。

可以将上述命令组合起来，比如：`pacman -Syyu` (强制更新软件源并更新软件)

### 搜索软件

`pacman -Ss [package-name]`

在 Arch Linux 和其衍生发行版中，pacman -Ss 是用于搜索软件包的命令。其中，-S 和 -s 是 pacman 命令的选项组合，具有以下含义：

-S 选项表示 --sync，意味着使用同步数据库来安装/更新软件包。
-s 选项表示 --search，意味着搜索软件包。

使用 `pacman -Ss` 命令时，pacman 将搜索软件包数据库中与提供的搜索项匹配的软件包。您可以提供一个或多个搜索项作为参数，以便 pacman 在软件包名称和描述中进行匹配搜索。

### 清理缓存

在 Arch Linux 和其衍生发行版中，pacman -Sc 是用于清理本地软件包缓存的命令。其中，-S 和 -c 是 pacman 命令的选项组合，具有以下含义：

-S 选项表示 --sync，意味着使用同步数据库来安装/更新软件包。
-c 选项表示 --clean，意味着清理本地软件包缓存。

使用 `pacman -Sc` 命令时，pacman 将删除本地软件包缓存中不再需要的软件包文件。这些软件包文件是在通过 pacman -S 或 pacman -Sy 命令安装或升级软件包时下载的。

### 删除软件

`pacman -R [package-name]`

在 Arch Linux 和其衍生发行版中，pacman -R 是用于删除已安装软件包的命令。其中，

-R 是 pacman 命令的选项，表示 --remove，意味着删除指定的软件包。

注意，这个命令只会删除指定的包，不会删除其依赖的一些包。

### 删除软件及其依赖

`pacman -Rs [package-name]`

在 Arch Linux 和其衍生发行版中，pacman -Rs 是用于删除已安装软件包及其不再被其他已安装软件包使用的依赖关系的命令。其中，-R 和 -s 是 pacman 命令的选项组合，具有以下含义：

-R 选项表示 --remove，意味着删除指定的软件包。
-s 选项表示 --recursive，意味着递归地删除不再被其他已安装软件包使用的依赖关系。

使用 pacman -Rs 命令时，您需要指定要删除的软件包的名称。pacman 将卸载并删除指定的软件包以及不再被其他已安装软件包使用的依赖关系。

### 删除软件及其依赖和配置文件

`pacman -Rns [package-name]`

在 Arch Linux 和其衍生发行版中，pacman -Rns 是用于删除已安装软件包及其依赖关系的命令，同时还会删除软件包的配置文件。其中，-R、-n 和 -s 是 pacman 命令的选项组合，具有以下含义：

-R 选项表示 --remove，意味着删除指定的软件包。
-n 选项表示 --nosave，意味着不保存软件包的配置文件。
-s 选项表示 --recursive，意味着递归地删除不再被其他已安装软件包使用的依赖关系。

使用 pacman -Rns 命令时，您需要指定要删除的软件包的名称。pacman 将卸载并删除指定的软件包以及不再被其他已安装软件包使用的依赖关系，并且还会删除软件包的配置文件。

### 查询系统安装软件

`pacman -Q`

在 Arch Linux 和其衍生发行版中，pacman -Q 是用于列出已安装软件包的命令。其中，

-Q 是 pacman 命令的选项，表示 --query，意味着查询已安装的软件包。

使用 pacman -Q 命令时，pacman 将列出系统中已经安装的所有软件包的名称和版本号。

**查询可结合管道符进行结果筛选，如：pacman -Q | wc -l 可查询安装的软件个数。**

### 查询显式安装（用户安装）软件

`pacman -Qe`

在 Arch Linux 和其衍生发行版中，pacman -Qe 是用于列出显式安装的软件包的命令。其中，

-Qe 是 pacman 命令的选项，表示 --query --explicit，意味着查询显式安装的软件包。

使用 pacman -Qe 命令时，pacman 将列出系统中显式安装的所有软件包的名称和版本号。显式安装的软件包是用户明确选择并手动安装的软件包，而不是作为依赖关系自动安装的软件包。

### 查询显式安装（用户安装）软件且不显示版本号

`pacman -Qeq`

在 Arch Linux 和其衍生发行版中，pacman -Qeq 是用于列出显式安装的软件包的名称的命令，以便进行查询或其他处理。其中，-Qeq 是 pacman 命令的选项组合，具有以下含义：

-Qe 选项表示 --query --explicit，意味着查询显式安装的软件包。
-q 选项表示 --quiet，意味着以静默模式输出，只显示软件包名称，而不显示版本号。

使用 pacman -Qeq 命令时，pacman 将以静默模式输出，仅列出系统中显式安装的所有软件包的名称。

### 根据文本查询安装的软件

`pacman -Qs [package-name]`

在 Arch Linux 和其衍生发行版中，pacman -Qs 是用于搜索已安装软件包的命令。其中，-Qs 是 pacman 命令的选项组合，具有以下含义：

-Q 选项表示 --query，意味着查询已安装的软件包。
-s 选项表示 --search，意味着搜索软件包。

使用 pacman -Qs 命令时，您需要指定要搜索的关键字。pacman 将搜索已安装的软件包名称和描述中包含指定关键字的软件包，并显示匹配结果。

### 查询已安装的且不再被依赖的软件

`pacman -Qdt [package-name]`

在 Arch Linux 和其衍生发行版中，pacman -Qdt 是用于列出已安装但不再被其他软件包所依赖的孤立软件包的命令。其中，-Qdt 是 pacman 命令的选项组合，具有以下含义：

-Q 选项表示 --query，意味着查询已安装的软件包。
-d 选项表示 --deps，意味着限制查询为仅显示依赖项。
-t 选项表示 --unrequired，意味着只显示不再被其他软件包所依赖的软件包。

使用 pacman -Qdt 命令时，pacman 将列出已安装的但不再被其他软件包所依赖的孤立软件包的名称。

### 删除所有已安装且不再被依赖的软件

`pacman -R $(pacman -Qdtq)`

注意，查询命令需要加上 -q，因为删除不能识别版本号。

## 配置文件

编辑配置文件：`sudo vim /etc/pacman.conf`

以下，是一些配置：

### Color

显示颜色，如版本号显示成绿色

### CheckSpace

检查是否存在剩余空间

### 软件源

编辑配置文件：`sudo vim /etc/pacman.conf`

在 Arch Linux 中，pacman.conf 是 pacman 包管理器的配置文件。它包含了用于定义软件包仓库和其他配置选项的节（sections）。

以下是一些常见的节及其含义：

[core]：这个节定义了 Arch Linux 官方软件包仓库（Core Repository）。它包含了 Arch Linux 系统所需的核心软件包，是系统的基础组件。

[extra]：这个节定义了 Arch Linux 官方软件包仓库（Extra Repository）。它包含了许多常用的软件包，不属于系统的核心组件，但仍然由 Arch Linux 官方维护。

[multilib]：这个节定义了 Arch Linux 官方软件包仓库的多架构支持（Multilib Repository）。Multilib 使得 Arch Linux 可以在 64 位系统上运行 32 位应用程序。该节包含了与多架构支持相关的软件包。

[archlinuxcn]：这个节定义了 Arch Linux 中的 Arch Linux 中文社区软件包仓库（Arch Linux Chinese Community Repository）。它是由 Arch Linux 中文社区维护的一个第三方软件包仓库，包含了一些常用的中文软件包和社区维护的软件包。

其中，格式如下：

```
[core]
Include = /etc/pacman.d/mirrorlist

[extra]
Include = /etc/pacman.d/mirrorlist

[multilib]
Include = /etc/pacman.d/mirrorlist # vim 中，使用 gf 跳转到对应文件

[archlinuxcn]
# 需要配置
SigLevel = Optional TrustedOnly
# SigLevel = Optional TrustAll
# 使用 Include 包含一个文件，文件内存储软件源
Include = /etc/pacman.d/archlinuxcn # 这个文件需要手动创建
# 或者，也可以使用 Server 直接写入软件源
# Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

其中，/etc/pacman.d/archlinuxcn 文件如下（注意，软件源的优先级是从上往下的，所以将速度快的源放到上面）：

```
# 清华大学（ipv4, ipv6, http, https)
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch

# CDN (ipv4, http, https)
Server = https://cdn.repo.archlinuxcn.org/$arch

# 浙江大学（ipv4, ipv6, http, https）
Server = https://mirrors.zju.edu.cn/archlinuxcn/$arch

# 中国科学技术大学（ipv4, ipv6, http, https）
Server = https://mirrors.ustc.edu.cn/archlinuxcn/$arch

# xTom 香港（ipv4, ipv6, http, https）
Server = https://mirror.xtom.com.hk/archlinuxcn/$arch

# Unique Studio 武汉（ipv4, http, https）
Server = https://mirrors.hustunique.com/archlinuxcn/$arch

# 上海科技大学（ipv4, http, https）
Server = https://mirrors-wan.geekpie.org/archlinuxcn/$arch

# 中国科学院开源软件协会 北京（ipv4, http）
Server = http://mirrors.opencas.org/archlinuxcn/$arch

# 电子科技大学凝聚网络安全工作室（ipv4, http）
Server = http://mirrors.cnssuestc.org/archlinuxcn/$arch

# 网易（ipv4, http）
Server = http://mirrors.163.com/archlinux-cn/$arch

# 重庆大学（ipv4, http）
Server = http://mirrors.cqu.edu.cn/archlinuxcn/$arch
```

## 参考教程

<iframe src="//player.bilibili.com/player.html?aid=55190132&bvid=BV1o4411N7oH&cid=96506566&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
