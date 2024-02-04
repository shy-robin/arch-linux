# 系统美化

## 设置 plasma

### 系统设置 -> 工作区行为 -> 桌面特效

- 关闭 “缩放（放大显示整个桌面，视图跟随鼠标移动）”
- 打开 “背景对比度（增强半透明窗口背景区域内容的对比度，改善其可读性）”
- 打开 “窗口背景虚化（对半透明窗口的背景进行虚化处理）”
- 打开 “窗口透明度（窗口在某些条件下呈现透明效果）”
- 打开 “非活动窗口变暗（非活动的窗口将会变暗）”
- 打卡 “请求管理员模式时降低屏幕亮度（系统请求 root 权限时降低屏幕亮度）”

点击右下角 “获取新桌面特效”
搜索 “scale expo”，点击安装

- 打开 “Scale OutExpo”

应用

### 系统设置 -> 工作区行为 -> 屏幕边缘

- 左上角点击，选择 “无操作”

应用

### 系统设置 -> 窗口管理 -> 任务切换器

主窗口，选择 “3D 封面切换”

应用

### 系统设置 -> 窗口管理 -> KWin 脚本

右下角获取新脚本，搜索 “blur”，安装 "forceblur-0.6.1.kwinscript"

勾选 Force Blur，点击应用。

## 下载资源

https://www.pling.com/p/1982010

下载里面的 3 个文件:

- plasmolds.zip
- fonts.zip
- backgrounds.zip

https://www.pling.com/p/1981573

下载里面的 4 个 latte 文件

## 安装主题

```
cd ~/Downloads

git clone https://github.com/linuxscoop/Relax-Plasma-Themes.git

cd Relax-Plasma-Themes

mkdir -p ~/.local/share/color-schemes && cp -Rv Relax\ Colorschemes/*.colors ~/.local/share/color-schemes/

mkdir -p ~/.themes && cp -Rv Relax\ GTK\ Themes/* ~/.themes

mkdir -p ~/.local/share/plasma/desktoptheme && cp -Rv Relax\ Plasma\ Themes/* ~/.local/share/plasma/desktoptheme

mkdir -p ~/.local/share/aurorae/themes && cp -Rv Relax\ Window\ Decotations/* ~/.local/share/aurorae/themes/

mkdir -p ~/.local/share/konsole/ && cp -Rv Relax\ Konsole\ Colorscheme/* ~/.local/share/konsole/
```

## 安装 kvantum 管理器和主题

`sudo pacman -S kvantum`

```
cd ~/Downloads/Relax-Plasma-Themes/

mkdir -p ~/.config/Kvantum && cp -Rv Relax\ Kvantum\ Themes/* ~/.config/Kvantum/
```

## 安装 icon 主题

```
cd ~/Downloads

git clone https://github.com/vinceliuice/Colloid-icon-theme.git

cd Colloid-icon-theme/

./install.sh -s default -t teal
```

## 安装 cursors 主题

```
cd ~/Downloads

git clone https://github.com/alvatip/Nordzy-cursors.git

cd Nordzy-cursors/

./install.sh
```

## 安装字体和壁纸

移动到 ~/Downloads 目录，解压 fonts.zip 压缩包到文件夹 fonts/，将 fonts/ 文件夹复制到 /home/.local/share 下

解压 backgrounds.zip 压缩包到文件夹 backgrounds/，将 backgrounds/ 文件夹复制到 /home/.local/share 下，重命名为 wallpapers/

## 应用主题、图标、光标、字体、墙纸

系统设置 -> 外观

- 应用程序风格：kvantum-dark
- Plasma 视觉风格：Relax-Plasma
- 窗口装饰元素：Relax-Blur-Aurorae
- 颜色：Relax-Dark-Color
- 字体：Source Code Pro
- 图标：Colloid-teal-Dark
- 光标：Nordzy 随便一个
- 欢迎屏幕：无

搜索 kvantum manager -> 变更/删除主题 -> 选择主题 Relax-Kvantum -> 应用此主题

右键桌面 -> 配置桌面和壁纸 -> 选择一张壁纸 -> 应用

logout

重新登录

系统设置 -> 外观 -> 窗口装饰元素 -> 标题栏按钮 -> 编辑布局并应用

## 安装 Plasmoid 窗口部件

```
cd ~/Downloads

unzip plasmoids*

cp -Rv plasmoids/* ~/.local/share/plasma/plasmoids
```

logout

重新登录

## 安装 Plasmoid 部件小程序

```
cd ~/Downloads

git clone https://github.com/psifidotos/applet-window-appmenu.git

cd applet-window-appmenu/

sudo pacman -S make cmake extra-cmake-modules

./install.sh
```

```
cd ~/Downloads

git clone https://github.com/psifidotos/applet-window-title.git

cd applet-window-title/

kpackagetool5 -i .
```

```
cd ~/Downloads

git clone https://github.com/psifidotos/applet-window-buttons.git

cd applet-window-buttons/

./install.sh
```

## 安装 latte dock 并导入 latte 布局

`sudo pacman -S latte-dock`

搜索 'autostart'， 添加应用程序 -> latte -> 应用

启动 latte

右键 latte dock -> 布局 -> 编辑布局 -> 导入 -> 从本地文件导入 -> Downloads/Unihalfy-single-p-single-d.layout.latte -> 应用

重复以上步骤，将剩余三个 latte 文件分别导入并应用

选中某个 layout，点击切换，可以看见布局会生效

右键底部栏 -> 进入编辑模式 -> 更多选项 -> 移除面板

系统设置 -> 工作区行为 -> 锁屏 -> 更换壁纸

右键桌面 -> 添加组件 -> 搜索 clock -> 移动到桌面调整位置

## 安装 SDDM 主题

```
cd ~/Downloads

git clone https://github.com/vinceliuice/Colloid-kde

cd Colloid-kde/sddm

./install.sh
```

系统设置 -> 开机与关机 -> 登录屏幕(SDDM) -> 选择 Colloid-dark -> 选择壁纸并应用

## 参考教程

<iframe src="//player.bilibili.com/player.html?aid=437327546&bvid=BV15j411V7JJ&cid=1018821485&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
