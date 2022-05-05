# 计算机网络与信息安全
## 考点 (8分左右)
![考点](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320154727.png)  

## 计算机网络
![计算机网络](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320155954.png)  
ARP: 地址解析协议  
RARP: 反向地址解析协议   
ICMP: 因特网控制协议  
IGMP: 网关信息协议  

物理层的协议:载波监听多路访问协议（CSMA）

### TCP和UDP的区别：
TCP: 传输控制协议  
UDP: 用户传输报文协议  
1、TCP面向连接（如打电话要先拨号建立连接）；UDP是无连接的，即发送数据之前不需要建立连接； 
2、TCP提供可靠的服务。也就是说，通过TCP连接传送的数据，无差错，不丢失，不重复，且按序到达；UDP尽最大努力交付，即不保证可靠交付；  
3、TCP面向字节流，实际上是TCP把数据看成一连串无结构的字节流；UDP是面向报文的；UDP没有拥塞控制，因此网络出现拥塞不会使源主机的发送速率降低（对实时应用很有用，如IP电话，实时视频会议等）；  
4、每一条TCP连接只能是点到点的；UDP支持一对一，一对多，多对一和多对多的交互通信；  
5、TCP首部开销20字节；UDP的首部开销小，只有8个字节；  
6、TCP的逻辑通信信道是全双工的可靠信道，UDP则是不可靠信道，整体来看UDP开销较小。

## TCP/IP网络协议族（重点）
下面的端口与协议均要记住  
CSMA:载波监听多路访问协议  
TokingRing: 令牌协议  
![TCP/IP网络协议族](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320160231.png)   
补充：  
> 左边的部分均为TCP协议,右边协议基于UDP协议。  
> https: 443端口   
> POP3 是邮件接收协议  
> SMTP 简单邮件接收协议  
> SNMP 是网络管理协议  
> NFS 网络文件系统  
> MIME 多用途互联网扩展邮件，是设定某种扩展名的文件用一种应用程序打开的方式类型，当该扩展名文件被访问的时候，浏览器会自动使用指定应用程序来打开。  
![TCP/IP协议族](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320161435.png)  

补充： 
POP3协议采用**Client/Server**模式进行通信，当客户机需要服务时，客户端软件与POP3服务器建立**TCP**链接。
*POP3（Post Office Protocol 3）即邮局协议的第3个版本，
它是规定个人计算机如何连接到互联网上的邮件服务器接收邮件的协议。
它是因特网电子邮件的第一个离线协议标准，POP3协议允许用户从服务器上把邮件存储到本地主机（即自己的计算机）上，
同时根据客户端的操作删除或保存在邮件服务器上的邮件，而POP3服务器则是遵循POP3协议的接收邮件服务器，
用来接收电子邮件的。POP3协议是TCP/IP协议族中的一员，由RFC 1939 定义。
本协议主要用于支持使用客户端远程管理在服务器上的电子邮件。
POP3协议采用的是C/S结构，同时该协议基于传输层TCP协议，所以客户端软件与POP3服务器会建立可靠的连接——TCP连接。*  
> URL:协议名://主机名.组名.最高层域名  

例如: http://xxxyftp.abc.can.cn   
http 协议名  
xxxyftp 主机名
abc.can 组名  
cn 最高层域名  

## IP地址
IP均为 IPV4协议,32位的;IPV6是128位地址       
IP分类取值范围,主要取决于主机号的位数。2^n -2 （排除全是0 和全是1的）  
A类: 0-127  
B类: 128-191  
![IP地址](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320162219.png)

## 子网划分
![子网划分](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320162333.png)
> 用主机号当子网与用部分网络号当子网  

注: **所有位数均为1的求出来的就是子网掩码**  
例题1:  
解题思路:   
首先题目中均为B类IP地址; 划分子网数 27个 需要用 2^5来表示;
且B类IP地址其网络号有16位,主机号有16位表示。  
因此需要*借用网络号5位来表示子网*;**子网掩码就是均为1的是子网掩码;**  
如下图 1111 1111 1111 1111 1111 1 即 255.255.248.0  
![子网掩码](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320163035.png)

例题2:  
700即 2^10 表示，即需要10位二进制;  
由于B类IP地址一共有16位网络号，16位主机号;因此*主机号占用10位来表示子网*，其余均为子网位。  
1111 1111 1111 1111 1111 11 即 255.255.252.0  
![子网掩码2](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320163346.png)  


## 网络规划与设计

![网络规划与设计](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320164903.png)
![层次化网络设计](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320164722.png)

## 计算机网络分类
10KM大概是局域网  
![计算机网络分类](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320164941.png)  
总线结构的:如果总线出故障，整体均不可用
核心的也是:核心出问题，均不可用。因此目前改进双核心结构

### 网络接入技术
![网络接入技术](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320165242.png)

### HTML
![HTML](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320165451.png)

## 对称加密技术 
### 考点(3分)
![对称加密技术](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320170407.png)  

### 对称加密技术
> 对称加密使用的同一套密钥,效率高但是安全性低  

![对称加密技术](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320170529.png)  

### 非对称加密技术
公钥私钥成对出现,发送者要用接受的公钥进行加密，接受者用自己的私钥进行解密。  
![非对称加密技术](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320171031.png)  

### 数字签名
证明文件是当前签发，用自己的私钥进行发送。接受者用A的公钥进行验证。   
![数字签名](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320171338.png)  

### 消息摘要
单向的加密，不能解密。只能用相同的方式进行加密，进行判断结果是否相等。   
![消息摘要](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320171806.png)

### PKI公钥体系
CA签发的密钥证书  
![PKI公钥体系](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220320171920.png)

## 网络安全
![网络安全](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321202236.png)  
TSL 是 SSL 3.0版本

## 网络攻击
### 被动攻击
<img alt="被动攻击" height="350" src="https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321202445.png" width="400"/>  

### 主动攻击
<img alt="主动攻击" height="350" src="https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321202406.png" width="400"/>

### Dos 与 DDos
服务忙于治理傀儡机而拒绝了正常的请求  
![Dos](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321202647.png)

## 防火墙
（这里截图截取不下）  
![防火墙左](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321203152.png)
![防火墙右](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321203042.png)

## 安全防护体系
正常有7层  
1. 物理环境的安全性  
2. 操作系统的安全性  
3. 网络的安全性  
4. 应用的安全性  
5. 管理的安全性  
![安全防护体系](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321203516.png)

## 计算机病毒与木马
![计算机病毒与木马](https://raw.githubusercontent.com/programmerIm/MyPictures/main/images/20220321203722.png)  
*木马主要是窃取，病毒是直接破坏电脑*

引导区病毒破坏的是引导盘、文件目录等    
宏病毒破坏的是OFFICE文件相关    
木马的作用一般强调控制操作。   
蠕虫病毒：  
震网（Stuxnet），指一种蠕虫病毒。它的复杂程度远超一般电脑黑客的能力。这种震网（Stuxnet）病毒于2010年6月首次被检测出来，是第一个专门定向攻击真实世界中基础（能源）设施的“蠕虫”病毒，比如核电站，水坝，国家电网。
“冲击波”病毒是一种蠕虫类型的病毒,在进行网络传播时，利用了Windows操作系统的RPC漏洞。