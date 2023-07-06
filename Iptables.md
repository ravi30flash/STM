## How to install iptables
```bash
    setenforce 0
    sed -i 's/^SELINUX=.*$/SELINUX=disabled/g' /etc/selinux/config
    yum install -y iptables
```

## How to save an iptable
`iptables-save [-c] [-t table_name]`