## How to install iptables
```bash
    setenforce 0
    sed -i 's/^SELINUX=.*$/SELINUX=disabled/g' /etc/selinux/config
    yum install -y iptables
```

## How to save an iptable
```bash
    iptables-save [-c] [-t table_name]
```
## How to see all iptable current rules
```bash
    iptables-save -L -v
```

## How to see all iptable INPUT rules
```bash
    iptables-save -L INPUT -nv
```

## How to block an ip address
```bash
    iptables -I INPUT -s 'ip_add' -j DROP
```

## How to block a network
```bash
    iptables -I INPUT -s 'network_add/24' -j DROP
```

## How to unblock an ip address
```bash
    iptables -D INPUT -s 'ip_add' -j DROP
```

## How to block all connections to a port
```bash
    # example to block 25 port
    iptables -A INPUT -p tcp --dport port_no -j DROP
    # iptables -A INPUT -p tcp --dport 25 -j DROP
    iptables -A INPUT -p udp --dport port_no -j DROP
    # iptables -A INPUT -p udp --dport 25 -j DROP
```
## How to enable  a port:
```bash
    # example to block 25 port
    iptables -A INPUT -p tcp --dport port_no -j ACCEPTST
    # iptables -A INPUT -p tcp --dport 25 -j ACCEPTST
    iptables -A INPUT -p udp --dport port_no -j ACCEPTST
    # iptables -A INPUT -p udp --dport 25 -j ACCEPTST
```

