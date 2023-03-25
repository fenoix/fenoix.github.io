---
title: Linux下Python的一些操作
tag: TeXt
tag: Linux
tag: Python
---



### Linux下后台运行python程序

```python
nohup python -u test.py > out.log 2>&1 &
nohup command > command.log 2>&1& echo $! > command.pid

nohup sh **.sh > /dev/null 2>&1 &
```

如上所示：

nohup  和  &  组合了后台运行程序。

可以输出到 out.log 保存程序输出，也可以输出到/dev/null 即空设备，不保存输出。

### 保存anaconda虚拟环境配置文件

```python
conda env export > enviroment.yaml   # 导出
conda env create -f environment.yaml   # 导入
```

### 查看cuda版本

```python
nvidia-smi   查看的是driver api对应的cuda版本
nvcc --version (-V)   查看的是runtime api对应的cuda版本  （装pytorch用这个）
通常，driver api的版本能向下兼容runtime api的版本，即nvidia-smi显示的版本大于nvcc --version，一般不会有问题。
```

[参考链接](https://www.jianshu.com/p/eb5335708f2a)

