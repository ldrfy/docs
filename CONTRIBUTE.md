# 贡献说明

我目前仅在 `archlinux最新版 gnome桌面环境(46)` 开发测试，使用gtk4，不支持旧版

ubuntu 需要 `23.10` 或 `24.04`

> ！！！尽可能少的依赖第三方库，或者这个库在各个发行版都很普遍也行，尽量不使用过时技术

## 待完成

- GTK4相关
    - [ ] 如何窗口置顶，暂时只能手动
    - [ ] 响应剪贴时如何弹出窗口到最上面，而不是显示“已就绪”，暂时非flatpak环境使用x11后端实现
    - [ ] 如何优雅的完成全局快捷键（尽量不使用过时的库，比如gtk3的，也不要使用root）
    - [ ] 如何优雅的显示状态栏图标（尽量不使用过时的库，比如gtk3的）

- wayland相关
    - `wayland` 环境下，不设置 `os.environ["GDK_BACKEND"] = "x11"`，如何复制立刻翻译，而不是鼠标移动到软件窗口才开始翻译


- 更多引擎，目前支持百度、谷歌、必应、腾讯、有道、火山，欢迎贡献
- 我英语不好，所以开发此项目。软件界面默认英文，有中文翻译，但是文档字太多，我只写中文……，其他人可以翻译文档，包括代码中的注释，也可以翻译


## 开发说明

下方仅对 archlinux 而言，ubuntu自己参考这里和 源码打包：`pkg/deb/DEBIAN/control`

### 编译工具 meson

```bash
sudo pacman -S meson appstream-glib zip uzip
```

### 依赖：

```bash
sudo pacman -S libadwaita python-gobject python-requests python-pyqt6 python-pillow qt6-svg
```


### 安装测试

安装在 `~/.local`

```bash
make test && lfy
```

卸载

```bash
make uninstall
```

### 打包

以下全部为测试，修改的文件及时生效

打包所有：

```bash
make release
```


#### pacman

```bash
# qt版本
make test-aur

# gtk版本
make BUILD_TYPE=gtk test-aur
```

文件生成在 `./disk/*.pkg.tar.zst`

安装

```bash
sudo pacman -U ./disk/*-qt.pkg.tar.zst

# gtk
sudo pacman -U ./disk/*-gtk.pkg.tar.zst
```

#### deb

工具

```bash
sudo pacman -S dpkg
```

```bash

# qt版本
make test-deb

# gtk版本
make BUILD_TYPE=gtk test-deb
```

文件生成在 `./disk/*.deb`

安装

```bash
sudo dpkg -i ./disk/*-qt.deb

# gtk
sudo dpkg -i ./disk/*-gtk.deb
```


#### rpm

fedora 和 opensuse 依赖名字不一样，所以分别打包了

工具

```bash
sudo pacman -S rpm-tools
```

```bash

# qt版本
make test-rpm

# gtk版本
make BUILD_TYPE=gtk test-rpm
```

文件生成在 `./disk/*.rpm`，opensuse系统的为 `./disk/*-suse.rpm`

安装

```bash
sudo dpkg -i ./disk/*-qt.rpm

# gtk
sudo dpkg -i ./disk/*-gtk.rpm
```


#### flatpak

工具

```bash
sudo pacman -S flatpak-builder
```

安装依赖

```bash
flatpak install flathub org.gnome.Platform//46 org.gnome.Sdk//46
```

```bash
make test-flatpak
```

文件生成在 `./disk/*.flatpak`



