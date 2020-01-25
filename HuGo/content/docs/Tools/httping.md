# httping

> Httping is like '[ping](http://en.wikipedia.org/wiki/Ping)' but for [http](http://en.wikipedia.org/wiki/Http)-requests. Give it an [url](http://en.wikipedia.org/wiki/Url), and it'll show you how long it takes to connect, send a request and retrieve the reply (only the headers). Be aware that the transmission across the network also takes time! So it measures the [latency](http://en.wikipedia.org/wiki/Latency_(engineering)) of the webserver + network. It supports, of course, IPv6.

`httping` 类似于 `ping` 命令，但是是发送 http 请求， 给它一个 url 链接， 它会返回请求这个链接的 连接、发送请求、接收响应的时间。主要用来衡量 **服务器和网络延时**。



## 安装

```bash
$ apt-get install httping # Debian/Ubuntu
$ yum install httping     # Fedora/CentOS/RHEL(EPEL源)
$ yaourt -S httping       # Arch Linux
$ emerge -av httping      # Funtoo/Gentoo
$ brew install httping    # MAC

$ httping --help
HTTPing v2.5, (C) 2003-2016 folkert@vanheusden.com
 * SSL support included (-l)
 * ncurses interface included (-K)

 *** where to connect to ***
-g x / --url             URL to ping (e.g. -g http://localhost/)
-h x / --hostname        hostname to ping (e.g. localhost) - use either -g or -h
-p x / --port            portnumber (e.g. 80) - use with -h
-6   / --ipv6            use IPv6 when resolving/connecting
-l   / --use-ssl         connect using SSL. pinging an https URL automatically enables this setting

...

```

## 常用参数

```bash
-K 使用图形模式

-g 要测量的网址
-l 使用 SSL 连接
-c 请求次数
-Y 启用颜色输出

-x ip:port 使用代理
-S 将时间分开成连接和传输两部分显示
-G GET(默认是HEAD)
-b 在使用了 GET 的前提下显示传输速度 KB/s
```

## 常用命令

```bash
# 
$ httping -g http://kail.xyz -Y
# 图形模式输出
$ httping -g http://kail.xyz -K
```



## 相关资料

- [httping 官网](https://www.vanheusden.com/httping/)