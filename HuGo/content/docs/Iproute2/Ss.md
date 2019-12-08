# ss

比 `netstat` 更好用的工具，`iproute2` 包附带的另一个工具

- 能够显示更多更详细的有关 TCP 和 连接状态 的信息
- 比 `netstat` 更快速更高效



## 常用参数

- `-n, --numeric` 不解析服务名称，同 `netstat`  
- `-a, --all`  显示所有套接字（sockets），同 `netstat`  
- `-l, --listening`  显示监听状态的套接字（sockets），同 `netstat`  
- `-t, --tcp` 仅显示 TCP套接字（sockets），同 `netstat`  
- `-u, --udp`       仅显示 UCP套接字（sockets），同 `netstat`  
- `-p, --processes`  显示使用套接字（socket）的进程，同 `netstat`  
- `-s, --summary`   显示套接字（socket）使用概况
- `-i, --info`      显示 TCP内部信息



## 常见场景

### 一般用法

```bash
# TCP 链接所在的进程
ss -antp
# 监听的网络端口和所在的进程
ss -lntp 
```

### Filter

```bash
# 匹配远程地址和端口号
ss dst 192.168.1.5
ss dst 192.168.119.113:http
ss dst 192.168.119.113:443

# 匹配本地地址和端口号
ss src 192.168.119.103:25

# ss dport OP PORT 远程端口和一个数比较
# ss sport OP PORT 本地端口和一个数比较
ss sport eq :22
ss state connected sport = :http
```



## Read More

- [ss 命令](https://wangchujiang.com/linux-command/c/ss.html)