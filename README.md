# blog
目前网络上有好多方法介绍如何通过某种手段来实现免费上网，看了这么多，发现主流的就两种方法，第一种方法是通过连接校园网时未登录状态下开放的53端口，把要访问的网站通过这个端口发出去，然后再从这个端口接收。这个方法可以实现绕过登陆上网，但是毕竟53端口不是专门传输数据的端口，访问速度限制很大，故舍去这种方法。现在主要介绍第二种方法

目录

原理

准备工作

1，首先需要一台国外的服务器，能同时访问ipv4和ipv6网络

2，然后在服务器上配置shadowsocks

3，客户端安装shadowsocks

4，客户端使用shadowsocks

注意事项

原理
由于校园网是ipv6访问不受限制的网络，所以可以利用校园网的这个特性，利用shadowsocks等socks5代理软件，把本机想要访问的http流量通过socks5代理转发出去，转发到一个能同时访问ipv6和ipv4的服务器上，然后这个服务器把本机要访问的流量再通过socks5用ipv6网络转发进来，这样就绕过了校园网登陆，同时也实现了科学上网和免费上网。

准备工作
1，首先需要一台国外的服务器，能同时访问ipv4和ipv6网络
个人经验比较推荐vultr上面的服务器，推荐配置是新加坡结点，Ubuntu18.04，3.5刀一个月。虽然日本离北方更近一点，但是vultr上日本的服务器大多数ip段都被封锁了，访问有很大限制，虽然速度更快一点但是有一些国内的网站上不去。新加坡结点的ip大多数还正常，访问速度尽管比日本的慢一点，但是基本能正常访问国内的所有网站。

2，然后在服务器上配置shadowsocks
有关服务器安装方面的问题可以参考一大神写的博客Ubuntu 16.04下Shadowsocks服务器端安装及优化

3，客户端安装shadowsocks
Windows用户下载：Releases · shadowsocks/shadowsocks-windows

macOS用户下载：Releases · shadowsocks/ShadowsocksX-NG

4，客户端使用shadowsocks
下载之后安装之后就可以添加配置好的服务器了



分别在这几个红框里添加之前配好的服务器地址（这个地址是服务器的ipv6地址），端口，密码，然后点击确定。

然后点击启用系统代理，勾选允许来自局域网的连接，并开启全局模式就行了



注意事项
1，在购买vultr服务器的时候，有一个enable ipv6 的选项要勾选上，意思就是给服务器提供ipv6地址

2，vultr充值一次要充10刀.....,按小时计费，上面可以实时显示目前的花费是多少

3，在服务器端配置shadow socks时可能会出现pip版本的问题，保证自己的pip版本是最新就行了

4，服务器分别提供了一个ipv4和ipv6地址，用shadowsocks连ipv6的地址用来免费上网，连ipv4的地址可以在任何网络条件下科学上网

5，手机上面也有socks5代理软件，由于安卓手机不支持ipv6故不能实现免费上网，但是可以连ipv4的地址进行科学上网，ios手机理论上是可以连ipv6地址的，但是上网效果不好。安卓手机shadowsocks可以在Google play上面搜到，ios用户下载socks5软件需要找一个国外的Apple id（某宝上有挺便宜的几块钱一个），然后搜索socks下载相应的软件，配置方法同电脑的配置方法。

6，这个方法虽然能实现免费上网，但是仍需要在服务器上投资，而且感觉并不是很划算，但是如果喜欢瞎折腾的话也不妨试试哈哈哈。

7，以上纯属个人经验，可能有些地方并不严谨，新手小白，大佬勿喷。

