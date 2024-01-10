---
title: iptables
date: 2024-01-10 11:03:51
tags:
---

```
# 查看 iptables
sudo iptables -t nat -vnL

# 修改端口映射
sudo iptables -t nat -A DOCKER -p tcp --dport 51876 -j DNAT --to-destination 172.19.0.4:80

# show line numbers
sudo iptables -t nat -vnL DOCKER --line-number

# 删除规则 3
sudo iptables -t nat -D DOCKER 3
```


