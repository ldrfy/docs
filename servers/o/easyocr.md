easyocr

设置中，可一次填写多个待识别语言，尽可能只填写自己需要的，填写过多可能识别出问题。

比如简体中文可填写 `ch_sim | en`， 即简体中文和英文，使用 `|` 分割。

具体支持的语言可在 [这里](https://www.jaided.ai/easyocr/) 查看

## 问题

首次识别时，如果模型下载失败，可以在这里下载，然后解压到 `~/.EasyOCR/model`

[模型下载](https://www.jaided.ai/easyocr/modelhub/)

目录下类似如下：

```bash
craft_mlt_25k.pth
english_g2.pth
zh_sim_g2.pth
```
