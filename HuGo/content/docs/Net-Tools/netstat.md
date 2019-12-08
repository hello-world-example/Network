# netstat

> Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships
>
> 打印网络连接、路由表、连接的数据统计、伪装连接以及广播域成员。



## 常用参数

- `-a --all` 显示所有选项，默认不显示 LISTEN 相关
  - `-t --tcp` 查询 **TCP 链接**
  - `-u --udp` 查询 UDP 链接
  - `-x --unix` 传车 UNIX 链接
- `-n --numeric` 直接**显示 IP 地址**，而不是域名
- `-p --programs` **显示 PID**，运行在 root 权限之下，才能得到运行在 root 权限下的进程名
  - MAC 下的 `-p ` 是 `protocl` 的意思，无法显示 PID，可以用 ` lsof -i :18080  ` 代替显示端口所在 PID
- `-l --listening` **显示监控中的服务器的 Socket**



- `-e --extend` 其他相关信息，比如搭配 `-pe` 显示进程用户
- `-i --interfaces` 网卡信息



- `-r --route`：显示Routing Table
- `-s --statistice`：显示网络工作信息统计表；



## 常见用法

### 列出所有的链接

```bash
netstat -an     # 列出所有当前的连接
netstat -ant    # 过滤出 tcp
netstat -anu    # 过滤出 udp
```
### 列出监听中的连接

```bash
# 不要使用 -a 选项，否则 netstat 会列出所有连接，而不仅仅是监听端口
netstat -ntl
# 或
netstat -ant | grep LISTEN
```






## Read More

- [netstat Manual](http://net-tools.sourceforge.net/man/netstat.8.html)
- [netstat 的10个基本用法](https://linux.cn/article-2434-1.html)
- [netstat 中文](https://wangchujiang.com/linux-command/c/netstat.html)