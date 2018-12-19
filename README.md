# pingtunnel
pingtunnel是把udp流量伪装成icmp流量进行转发的工具，类似于kcptun。
典型的使用方式
![image](network.jpg)

    通过伪造ping，把udp流量通过远程服务器转发到目的服务器上。用于突破某些运营商封锁UDP流量。
    By forging ping, the udp traffic is forwarded to the destination server through the remote server. Used to break certain operators to block UDP traffic.

    Usage:

    pingtunnel -type server

    pingtunnel -type client -l LOCAL_IP:4455 -s SERVER_IP -t SERVER_IP:4455

    -type     服务器或者客户端
              client or server

    -l        本地的地址，发到这个端口的流量将转发到服务器
              Local address, traffic sent to this port will be forwarded to the server

    -s        服务器的地址，流量将通过隧道转发到这个服务器
              The address of the server, the traffic will be forwarded to this server through the tunnel

    -t        远端服务器转发的目的地址，流量将转发到这个地址
              Destination address forwarded by the remote server, traffic will be forwarded to this address

    -timeout  本地记录连接超时的时间，单位是秒
              The time when the local record connection timed out, in seconds

    -sproto   客户端发送ping协议的协议，默认是13
              The protocol that the client sends the ping. The default is 13.

    -rproto   客户端接收ping协议的协议，默认是14
              The protocol that the client receives the ping. The default is 14.
