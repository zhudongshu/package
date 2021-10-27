# package

### 第一步 创建文件夹结构
```markdown
文件夹名
   | -- LICENSE
   | -- 文件夹名
   |       | -- __init__.py
   |       | -- 文件夹名.py
   | -- README.md
   | -- setup.py
```
 
### 第二步 文件写入
```python
(1) __init__.py
    from __future__ import absolute_import
    from .文件夹名 import *
    
    name = '文件夹名'
```
```python
(2) 文件夹名.py
    def output():
        print('这是我第一个python包!')
```
```markdown
(3) README.md
    一些介绍包功能的描述 技术文档
```
```python
(4) setup.py
    import setuptools
    
    with open('README.md','r') as fh:
        long_description = fh.read()
    
    setuptools.setuo(
        name = '包名',
        version = '版本号',
        author = '用户名',
        author_email = '邮箱',
        description = '描述',
        long_description = long_description,
        long_description_content_type = 'text/markdown',
        url = 'https://upload.pypi.org/legacy',
        packages = setuptools.find_packages(),
        classifiers = [
            'Programming Language :: Python :: 3'
        ], # 文件使用的版本号，安全等等
    )
```

### 第三步 将包上传到pypi
```markdown
1. pip install twine
2. python setup.py sdist
3. python setup.py install
4. twine upload dist/*
```
