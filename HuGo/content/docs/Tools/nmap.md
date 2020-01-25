# nmap

> - [nmap 官网](https://nmap.org/)
> - [nmap 中文网](http://www.nmap.com.cn/)

## 简介

- 网络扫描和嗅探工具包
- 系统漏洞扫描之王

## 常见用法

### 端口扫描

```bash
# 不指定要扫描的端口，默认扫描 1-1024, 再加上 https://svn.nmap.org/nmap/nmap-services 著名端口
ᐅ nmap 127.0.0.1
# 扫描所有端口，可能需要 20分钟
ᐅ nmap 127.0.0.1 -p1-65535
# 多个范围用 逗号分割
ᐅ nmap 127.0.0.1 -p1000-2000,9999,8080-9000


# 结果示例
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00024s latency).
Not shown: 962 closed ports, 29 filtered ports
PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
445/tcp   open  microsoft-ds
548/tcp   open  afp
1086/tcp  open  cplscrambler-lg
1087/tcp  open  cplscrambler-in
1089/tcp  open  ff-annunc
7070/tcp  open  realserver
10000/tcp open  snet-sensor-mgmt
```

### IP 扫描

```bash
# 扫描多个 IP
ᐅ nmap 127.0.0.1  192.168.1.1

# 多个用逗号分割
ᐅ nmap 192.168.1.1,2,3,4
# 连续的 IP
ᐅ nmap 192.168.1.1-4
Nmap scan report for 192.168.1.1
Host is up (0.12s latency).
Not shown: 998 filtered ports
PORT     STATE SERVICE
80/tcp   open  http
1900/tcp open  upnp
Nmap done: 4 IP addresses (1 host up) scanned in 15.11 seconds

# 扫描一个子网网段所有IP
ᐅ nmap 192.168.1.0/24
# 排除某个 IP
ᐅ nmap 192.168.1.0/24  --exclude 192.168.1.162
```





## Read More

- [nmap超详细使用指南](https://crayon-xin.github.io/2018/08/12/nmap%E8%B6%85%E8%AF%A6%E7%BB%86%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97/)