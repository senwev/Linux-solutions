# Linux 系统 相关问题解决方案

## Cent OS 安装FTP服务


```bash
rpm -qa | grep vsftpd
sudo yum install apt
```
安装完成后吧 /etc/vsftpd/vsftpd.conf中的
anonymous_enable=Yes 改为 anonymous_enable=FALSE

开启vsftpd服务
```bash
systemctl start vsftpd
```

查询端口是否开启成功
```bash
netstat -ano | grep '21'
```
成功会显示 tcp6 :::21

最后要去除用户屏蔽，把/etc/vsftpd/ftpusers 和 /etc/vsftpd/user_list 中的root(如果要用root登录的话)删掉就可以了
