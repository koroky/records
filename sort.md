# Sort 命令
Linux **sort** 是一个用来对内容进行排序的命令

`sort [OPTION]... [FILE]...`

### 使用方法
```
-i         忽略非ASCII字符
-r         输出反序
-t         行分隔符（默认为空白字符）
-k         以第k列作为排序列
-c         检查是否已排好序
-n         以数字序来排序
-h         以人类可读的数字来排序
```


### 使用示例
```sh
# 按照第二列排列（按字母表的顺序）/目录下所有文件与目录
ls -lt / | sort -k2

# 按照第二列的数字排列/目录下所有文件与目录
ls -lt / | sort -n -k2

# 按照第二列的数字倒序排列/目录下所有文件与目录
ls -lt / | sort -n -k2

# 按照第六列的月份排列/目录下所有文件与目录
ls -lt / | sort -M -k6

# 按照第五列的大小（b->k->M->G...）排列/目录下所有文件与目录
ls -lht / | sort -h -k5
```