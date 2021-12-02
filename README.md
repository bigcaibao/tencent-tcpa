# tencent-tcpa
来自腾讯的tcp单边加速方案
<!--
注意:
```
系统最好是centos7或者以上
boot分区大于500M,否则可能会安装内核失败
```  

安装:  
一键安装:
```
wget https://raw.githubusercontent.com/bigcaibao/tencent-tcpa/tcpa.sh
chmod +x tcpa.sh
sh tcpa.sh
```

手动安装:  
安装必要依赖:
```
yum -y install net-tools
```
更换系统内核:
```
wget https://github.com/bigcaibao/tencent-tcpa/releases/download/1.0/kernel-3.10.0-693.5.2.tcpa06.tl2.x86_64.rpm
rpm -ivh kernel-3.10.0-693.5.2.tcpa06.tl2.x86_64.rpm --force
```
重启:
```
reboot
```
下载tcpa解压并安装
```
wget https://github.com/bigcaibao/tencent-tcpa/tcpa_packets_180619_1151.tar.gz
tar zxvf tcpa_packets_180619_1151.tar.gz
cd tcpa_packets
sh install.sh
```
================================  

TCPA(默认只加速80,443,8080这3个端口)，如需新增加速端口请编辑如下:
```
vim /usr/local/storage/tcpav2/start.sh
```
第46行后添加:
```
$BINDIR/$CTLAPP access add tip $ip tport 自定义端口
```
启动tcpa拥塞算法:
```
cd /usr/local/storage/tcpav2
sh start.sh
```

卸载:
```
cd /usr/local/storage/tcpav2  
sh uninstall.sh
```
--!>
