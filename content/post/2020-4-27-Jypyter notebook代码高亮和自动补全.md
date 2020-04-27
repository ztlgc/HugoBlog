---
title: Jypyter notebook代码高亮和自动补全
subtitle: Jypyter notebook代码高亮和自动补全
date: 2020-04-17
tags: ["python", "jupyter"]
---


>  `Jupyter notebook` 的代码高亮和自动补全等功能由`Jypyter` 插件`jupyter_contrib_nbextensions` 实现

# 1、安装 

### conda 

1. 建议先升级 conda

```shell
conda update -n base conda
```

2. 开始安装

```shell
conda install -c conda-forge jupyter_contrib_nbextensions
```

###  PIP

1. 也建议升级PIP

```python
 python -m pip install --upgrade pip
```

2. 开始安装

```shell
pip install jupyter_contrib_nbextensions
```


# 2、启用

点击取消保护，接下来就可以定制自己的 Jupyter 了

![JheifU.png](https://s1.ax1x.com/2020/04/27/JheifU.png)

比较常用的有：

**AutoSaveTime**  ：自动保存

**Codefolding in Editor** ： 代码折叠

**Table of Contents** ：自动生成目录插件

**Autopep8：** 自动代码格式优化



最后想深入了解的话，该软件包的 GitHub 地址为： [GitHub](https://github.com/ipython-contrib/jupyter_contrib_nbextensions)