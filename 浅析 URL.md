## URL的组成
1. 协议（http或https）
    * **HTTP协议是基于TCP和IP连个协议的协议**
2. 域名或IP
    * 浏览器会现在本地的host文件查找有没有对应的地址，没有找到的话会通过DNS服务找到IP地址
    * www是二级域名，这是历史遗留问题，并不是网站需要www才可以访问
3. 端口
    http对应的端口是80，https是443，ftp是21
    端口可以不输入，默认会根据协议默认值访问
4. 路径
    假设不输入路径，直接访问`google.com`，会自动访问`google.com/`根路径
5. 参数
    使用`?`与前面的路径分割开，可以有多个参数，每个参数使用`&`分割
6. 锚点
    使用`#`指定锚点，锚点不会发送到服务器，浏览器会对锚点进行对位，是本地的一个操作
    
## DNS
* 全程是Domain Name System ，域名系统
* 将域名解析为IP地址，使得用户不需要记住复杂的数字，通过域名就可以访问

* 使用`nslookup`命令可以找到域名所对应的ip地址
![](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595388404509.png?x-oss-process=style/pic)

# IP
* 全称是 Internet Protocol 互联网协议
* 约定了两件事
    1. 如何定位一台设备
    2. 如何封装数据报文（请求是什么格式、响应是什么格式）
* 127.0.0.1表示当前设备
* ping命令可以对一个网络地址发送测试数据包，看该网络地址是否有响应并统计响应时间，以此测试网络。
    ![](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595388423059.png?x-oss-process=style/pic)
    
## www
www = URL + HTTP + HTML

## 路由器
路由器具有两个Ip，一个是内网IP，一个是外网IP，内网中的设备可以互相访问，但是不能直接访问外网，内网的设备想要访问外网，必须通过路由器中转，由路由器发起请求，外网中的设备也不能直接访问到内网中的设备，外网设备要想把内容发到内网，也必须通过路由器，所以路由器也称为网关。


