## Linux防火墙

### iptables

-启动iptables(本次启动)
```service iptables start```

-启动iptables(永久生效)
``` chkconfig iptables on```

- 关闭iptables
```service iptables stop```

- 关闭iptables(永久生效)
```chkconfig iptables off```

- iptable状态
```service iptables status```

### firewalld

Centos 7 默认使用firewalld

-停止firewall
```systemctl stop firewalld.service```

-禁止firewall开机启动
```systemctl disable firewalld.service```