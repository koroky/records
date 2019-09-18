# Crontab 命令
Linux **crontab** 是一个设置定时执行任务的命令

`crontab [ -u user ] [ -i ] { -e | -l | -r }`

### 使用方法
```
-e      编辑用户的定时任务 
-l      列出用户的定时任务
-r      删除用户的定时任务
```


### 使用示例
```sh
# 编辑当前用户的定时任务
crontab -e

# 编辑 nginx 用户的定时任务
crontab -u nginx -e

# 显示 nginx 用户的定时任务
crontab -u nginx -l
```


### 配置文件
系统级的定时任务文件位于：`/etc/cron.*/` 目录下
用户级的定时任务文件位于：`/var/spool/cron/` 目录下

