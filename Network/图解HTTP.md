#### 图解HTTP
##### 1. TCP/IP协议层
- 应用层(FTP, DNS, HTTPS等):                                                                                                       应用层决定了向用户提供应用服务时通信的活动.
- 传输层(TCP,UDP):传输层对上层应用层, 提供处于网络连接中的两台计算机之间的数据传输.
- 网络层:网络层用来处理在网络上流动的数据包.数据包是网络传输的最新单位,该层规定了通过怎样的路径达到对方计算机,并把数据包传给对方.
- 链路层:用来处理连接网络的 2.硬件部分.

#### 2. IP协议
网际协议位于网络层, 就是把各种数据包传送给对方, 保证送达到对方的两个重要条件就是IP地址和MAC地址.
IP地址指明了节点被分配到的地址, MAC地址是指网卡所属的固定地址.
IP件的通信依靠MAC地址, 会采用ARP协议:解析地址协议, 根据通信双方的IP地址就可以反查出MAC地址.

#### 3.TCP协议
TCP协议位于传输层, 提供可靠的字节流服务.采用三次握手保证是否成功送达.
- 1.发送端发送一个带SYN标志的数据包给对方
- 2.接收端接收后,回传一个带有SYN/ACK标志的数据包以示传达确认信息.
- 3.发送端在回传一个带ACK标志得数据包, 代表握手结束.
如果某个过程中莫名中断,TCP协议会以相同的顺序发相同的数据包. 除了三次握手, TCP协议还有其他手段来保证通信的可靠性.

#### 4.DNS协议
DNS协议和HTTP协议同属于应用层, 它提供域名到IP之间的解析服务.

#### 5.HTTP方法
- 1.GET:获取资源.
- 2.POST:传输实体主体.
- 3.PUT:传输文件.
- 4.HEAD:获取报文首部, 只是不返回报文主体部分,用于确认URL的有效性和资源的更新时间等.
- 5.DELETE:删除文件.
- 6.OPTIONS:询问支持的方法.
- 7.TRACE:让web服务器将之前的请求通信环回给客户端的方法.
- 8.CONNECT:要求用隧道协议连接代理.