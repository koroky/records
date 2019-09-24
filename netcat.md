# netcat 命令
Linux **netcat** 是一个用来调试 TCP/UDP 网络连接的工具

`nc [-46bCDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl] [-m minttl] [-O length] [-P proxy_username] [-p source_port] [-q seconds] [-s source] [-T keyword] [-V rtable] [-W recvlimit] [-w timeout] [-X proxy_protocol] [-x proxy_address[:port]] [-Z peercertfile] [destination] [port]`

### 使用方法
```
-l         监听某个端口
-u         使用UDP模式（默认为TCP）
-w         超时时间（对监听模式不起作用）
-n         不使用地址解析（即）
-p         使用端口号
-v         显示详细信息（类似于Debug日志）
-z         连接成功后，不发送信息即断开
-k         保持监听状态不断开（接收完一个请求后不退出）
```


### 使用示例
```sh
# 使用本地端口号 31337 来连接 host.example.com 主机的 42 端口，超时时间为 5 秒
nc -p 31337 -w 5 host.example.com 42

# 连接到 host.example.com 的 53 端口
nc -u host.example.com 53

# 扫描 192.168.1.5 主机的 1 到 1024 端口，查看是否开放端口
nc -znv 192.168.1.5 1-1024

# 访问百度网站
printf "GET / HTTP/1.0\r\n\r\n" | nc www.baidu.com 80
```
