---
title: Python 如何发包
date: 2018-04-04 18:33:39
tags: 
  - Python
---


<!--提纲-->
<!--发包方案-->
<!--测试-->
<!--目录结构-->


### 0. 简介
前段时间因为要发布自己的第一个 Python 包 `macCC`, 所以摸索了一下 Python pip 包的发包流程，这里分享出来，希望对大家有所帮助，有疑问的话可以微信:`cijianzy`,或者邮箱`cijianzy@gmail.com`联系我一起交流。

### 1. 依赖安装

```
python -m pip install --upgrade pip setuptools wheel
```

### 2. setup.py 

在工程的根目录创建 `setup.py`,填入以下以下工程配置，

```
from setuptools import setup, find_packages

setup(name='YOUR_PROJECT_NAME',
      version='0.0.1',
      author="YOUR_NICKNAME",
      author_email="YOUR_EMAIL",
      url="PROJECT_WEBSITE",
      #packages=find_packages(), 
      packages=['YOUR_PROJECT_SOURCE_DIR'],
      description=("YOUR_PROJECT_DESCRIPTION"),
      long_description=open('README.md').read(),
      install_requires=['Pillow'],
      classifiers=[
          "Programming Language :: Python",
          "License :: OSI Approved :: MIT License",
          "Development Status :: 3 - Alpha"
          ]
      )

```


### 3. 测试

完成配置以后，即可通过本地安装测试

```
pip install .
```


### 4. 发布账号注册

发布前，需要在下面地址进行账号注册发布账号注册并完善本地配置文件信息：

[账号注册](https://pypi.python.org/pypi?%3Aaction=register_form)


创建配置文件`~/.pypirc`，填入以下内容

```
[distutils]
index-servers =
    pypi

[pypi]
repository: https://upload.pypi.org/legacy/
username: YOUR_USER_NAME
password: YOUR_USER_PASSWORD
```


### 5. 发布&升级

上面的流程全部走完以后，即可进行发布了，根目录执行如下命令进行提交发布

```
python setup.py register sdist upload
```

发布以后即可进行升级了

```
rm -rf ~/Library/Caches/pip && pip install YOUR_PROJECT_NAME --upgrade
```


