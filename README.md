# 兰译 lfy <img src="images/cool.ldr.lfy.svg" width = "36" height = "36" alt="兰译" align=center />

此为[ldr-translate](https://github.com/yuhldr/ldr-translate) 重构版， [ldr-translate](https://github.com/yuhldr/ldr-translate) 还能用，但是不再更新，旧系统可以使用它，还是挺好用的，但是我喜欢挑战新技术。

<center>
<div style="display: flex;">
    <img src="images/main.png" alt="首页" style="width: 40%;">
    <img src="images/preference.png" alt="设置1" style="width: 25%;">
    <img src="images/server-preference.png" alt="设置2" style="width: 25%;">
</div>
</center>


## 优势：

- [x] 占用极小，不到 `0.2M`
- [x] 复制，自动翻译并弹窗
- [x] 支持 `gnome` 原生 `libadwaita`，简洁、美观！
- [x] 提供多种打包格式，预计推出 `archlinux` `deb` 等
- [x] 多引擎支持，目前 `百度、腾讯、谷歌、有道`，未来预计更多
- [x] 界面支持多国语言，使用 `gettext`

## 使用方法


> 有些不方便，不能直接响应快捷键、窗口置顶、剪贴板，应该是wayland的问题，有解决方案的化可以看 [贡献说明](CONTRIBUTE.md)


推荐在系统设置添加快捷键，自己去系统设置里，设置为 `lfy` 自定义 `快捷键`（比如 `Ctrl alt L`）

然后，每次需要翻译时，先复制翻译文本，再点 `快捷键` 即可，你可以把这个窗口右键置顶，也可以关闭


## 其他

> 我英语不好，所以开发此项目。软件界面默认英文，有中文翻译，但是文档字太多，我只写中文……，其他人可以翻译文档，包括代码中的注释，也可以翻译

- [贡献说明](CONTRIBUTE.md)

- [翻译说明](TRANSLATE.md)

- [更新说明](CONTRIBUTE.md)


部分代码参考：

- [gnome-music](https://gitlab.gnome.org/GNOME/gnome-music)
- [dialect](https://github.com/dialect-app/dialect)
