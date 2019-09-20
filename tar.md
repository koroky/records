# Tar 命令
Linux **tar** 是一个用来打包归档文件或目录以及解包的命令

**tar** 命令有三种使用方式：
1. 传统方式  `tar {A|c|d|r|t|u|x}[GnSkUWOmpsMBiajJzZhPlRvwo] [ARG...]`
2. Unix 方式  `tar -c [-f ARCHIVE] [OPTIONS] [FILE...]`
3. GNU 方式  `tar --create [--file ARCHIVE] [OPTIONS] [FILE...]`

其中 GNU 方式使用长选项，前面两种区别在于是否在参数前使用`-`符号。这里主要介绍前两种使用的方式

### 使用方法
```
c   创建一个归档文件
x   解开一个归档文件
v   打印出步骤信息（类似于Debug日志）
f   文件名
t   查看归档中文件列表
j   使用 bzip2 算法压缩/解压
z   使用 gzip 算法压缩/解压
r   添加文件或目录到归档文件中
W   检查归档文件
```


### 使用示例
```sh
# 查看包里文件与目录
tar tf XXX.tar.gz
tar tf XXX.tar

# 只解压出某一个文件或目录
tar xvf XXX.tar [FILE...]
tar xvf XXX.tar.gz [FILE...]
tar xvf XXX.tar.bz2 [FILE...]

# 解压到某一指定位置
tar -C LOCATION xvf XXX.tar.gz

# 打包文件与目录
tar cvf XXX.tar [FILE...]              # 不作压缩
tar czvf XXX.tar.gz [FILE...]          # 使用 gzip 算法压缩
tar cjvf XXX.tar.bz2 [FILE...]         # 使用 bzip2 算法压缩

# 添加文件或目录到压缩包
tar -rvf XXX.tar [FILES...]

```







