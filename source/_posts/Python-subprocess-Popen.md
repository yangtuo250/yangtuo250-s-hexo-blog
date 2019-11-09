---
title: Python subprocess.Popen 两种使用方式
date: 2019-10-23 22:19:34
category: Python
tags: [Python, subprocess]
---
### 需求是捕捉到另外一个程序的运行情况，获取错误信息
<!-- more -->
## 1. 直接调用Popen
```python
"""
test.py
"""
import time
import tensorflow

for i in range(3):
    print("sb subprocess")
    time.sleep(2)
```
```python
import subprocess

result = subprocess.Popen("python -u test.py", shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE)

while 1:
    err = result.stderr.readline()
    print(err)
    # if Traceback in one line of stderr, then print rest errors all
    if "Traceback" in err:
        print(result.stderr.readlines())
```
直接调用Popen可以异步等待result生成
## 2. 使用Popen.communicate()
```python
import subprocess

result = subprocess.Popen("python -u test.py", shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE).communicate()

if "Traceback" in result[1].decode():
    print(result[1].decode())
```
使用Popen的communicate()方法，会阻塞在result语句。

生成的result是一个二元tupple，（stdout, stderr）