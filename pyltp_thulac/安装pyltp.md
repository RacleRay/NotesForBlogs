pyltp Git：https://github.com/HIT-SCIR/pyltp

LTP C++ Git：https://github.com/HIT-SCIR/ltp



# 安装 pyltp

文档：https://pyltp.readthedocs.io/zh_CN/latest/

- 注：由于新版本增加了新的第三方依赖如dynet等，不再支持 windows 下 python2 环境。

## 使用 pip 安装

使用 pip 安装前，请确保您已安装了 [pip](https://pip.pypa.io/)，编译需要MSVC Build tools，14.0版本

> Install Visual C++ 2015 Build Tools from https://go.microsoft.com/fwlink/?LinkId=691126 with default selection.

```
$ pip install pyltp
```

接下来，需要下载 LTP 模型文件。

> - 下载地址 - [模型下载](http://pan.baidu.com/share/link?shareid=1988562907&uk=2738088569)
> - 当前模型版本 - 3.4.0
> - 注意在windows下 3.4.0 版本的 语义角色标注模块([pisrl.model](http://model.scir.yunfutech.com/server/3.4.0/pisrl_win.model)) 模型需要单独下载，具体查看下载地址链接中的说明。

请确保下载的模型版本与当前版本的 pyltp 对应，否则会导致程序无法正确加载模型。



## 从源码安装

您也可以选择从源代码编译安装

```
$ git clone https://github.com/HIT-SCIR/pyltp
$ git submodule init
$ git submodule update
$ python setup.py install
```

安装完毕后，也需要下载相应版本的 LTP 模型文件。



## Wheel安装

[py3.5](http://mlln.cn/2018/01/31/pyltp%E5%9C%A8windows%E4%B8%8B%E7%9A%84%E7%BC%96%E8%AF%91%E5%AE%89%E8%A3%85/pyltp-0.2.1-cp35-cp35m-win_amd64.whl)

[py3.6](http://mlln.cn/2018/01/31/pyltp%E5%9C%A8windows%E4%B8%8B%E7%9A%84%E7%BC%96%E8%AF%91%E5%AE%89%E8%A3%85/pyltp-0.2.1-cp36-cp36m-win_amd64.whl)

本地编译Wheel：

```
sudo python3 setup.py bdist_wheel 

cd dist/
```



## 使用教程

https://pyltp.readthedocs.io/zh_CN/latest/api.html#id2





# C++ LTP

文档：http://ltp.ai/docs/install.html#ltp

需要手动编译，准备CMAKE，windows还要 Visual Studio

在 `bin/examples` 目录下生成以下二进制程序:

| 程序名        | 说明                       |
| :------------ | :------------------------- |
| `cws_cmdline` | 分词模块命令行程序         |
| `pos_cmdline` | 词性标注模块命令行程序     |
| `ner_cmdline` | 命名实体识别模块命令行程序 |
| `par_cmdline` | 依存句法分析模块命令行程序 |

> 在window版本中 `ltp_server` 、`Maxent` 、`SRLExtract` 、`SRLGetInstance` 并不被编译



在 `lib` 目录下生成以下静态链接库 :

| 程序名          | 说明              |
| :-------------- | :---------------- |
| `splitsnt.lib`  | 分句lib库         |
| `segmentor.lib` | 分词lib库         |
| `postagger.lib` | 词性标注lib库     |
| `parser.lib`    | 依存句法分析lib库 |
| `ner.lib`       | 命名实体识别lib库 |
| `srl.lib`       | 语义角色标注lib库 |

> window下产生的静态库的后缀是.lib，linux下产生的静态库的后缀是.a