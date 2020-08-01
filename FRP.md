# 在CentOS 上面安装FRP服务端

1.下载所需包
```bash
wget https://github.com/fatedier/frp/releases/download/v0.13.0/frp_0.13.0_linux_amd64.tar.gz
```

2.创建目录并解压放置
```bash
mkdir -p /usr/local/frp
mv frp_0.13.0_linux_amd64.tar.gz /usr/local/frp
cd /usr/local/frp

sudo tar -zxvf frp_0.13.0_linux_amd64.tar.gz
cd frp_0.13.0_linux_amd64
rm frpc frpc.ini 
#frpc、frpc.ini为客户端配置文件，frps、frps.ini为服务端配置文件，此处删除客户端配置文件
```

3.进行服务端配置
```bash
vi frps.ini
```

   [common]
   bind_port = 7000                # 与客户端绑定的进行通信的端口，两端需一致
   vhost_http_port = 6081      # 访问客户端web服务自定义的端口号，任意一个没使用的端口号都可以
   
   
   :wq 
   
   保存并退出
   
4.运行
```bash
nohup ./frps -c ./frps.ini &   # 后台运行
```
