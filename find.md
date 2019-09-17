# Find 命令
Linux **find** 是一个用来查找文件或目录的命令

`find [-H] [-L] [-P] [-D debugopts] [-Olevel] [starting-point...] [expression]`

### 使用方法
```
-type         查找类型，包括: f (文件), d (目录), l (链接)等
-name/-iname  名称匹配（其中-iname表示不区分大小写）
-regex        使用正则表达式进行匹配
-size n       大小为 n 的文件
-user USER    属于某个用户的文件
-empty        为空的（文件或目录）
-delete       删除查找到的文件（**注意**，不要将些选项放到命令前面，请放到匹配的最后面）
```


### 使用示例
```sh
# 查找当前目录下的 JavaScript 文件
find . -type f -name '*.js'

# 查找 /bin 与 /usr/bin 下的**find**命令
find /bin /usr/bin -name 'find'

# 查找 ubuntu 用户的日志文件
find /var/log -user ubuntu -type f -name '*.log'

# 查找 /var/log 目录下的空目录
find /var/log -type d -empty

# 查找 /var/log 目录下（不递归）大小大于10M的文件
find /var/log -maxdepth 1 -type f -size +10M

# 删除找到的文件（注意此处 -delete 的位置）
find /var/log -type f -size +10M -name '*.log' -delete
# find /var/log -delete -type f -name 'abc.log'     # 这条语句会删除 /var/log 下的所有文件，而不是仅仅 abc.log
```

