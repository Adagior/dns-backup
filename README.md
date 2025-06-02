smartdns

https://github.com/mokeyish/smartdns-rs
```
smartdns run -c ./smartdns.conf -d

smartdns service help

   in-addr.arpa


server https://1.2.4.8/dns-query  -bootstrap-dns -exclude-default-group
server https://8.8.8.8/dns-query  -bootstrap-dns -exclude-default-group

```






https://github.com/cachefiles/dnsfix/wiki/%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95

n.yiz.me

https://ilpl.me/2018/08/17/public-DNS-5353-list/ https://www.publicdns.xyz/


bind
```
yum install bind

systemctl start named
systemctl enable named

vi /etc/named.conf


netstat -tlunp | grep 53
```

coredns-backup

```
tar zxvf
nohup ./coredns >/dev/null 2>&1 

https://github.com/coredns/coredns
```

```
.:53{
    forward . 208.67.222.222:443 208.67.222.222:5353 208.67.220.220:443 208.67.220.220:5353
    log
    health
}
```
```
.:53{
    forward . 127.0.0.1:5301 127.0.0.1:5302 127.0.0.1:5303
    log
    health
}
.:5301 {
   forward . tls://9.9.9.9 {
       tls_servername dns.quad9.net
   }
   cache
}
.:5302 {
    forward . tls://1.1.1.1 tls://1.0.0.1 {
        tls_servername 1dot1dot1dot1.cloudflare-dns.com
    }
    cache
}
.:5303 {
    forward . tls://8.8.8.8 tls://8.8.4.4 {
        tls_servername dns.google
    }
    cache
}
```

https://laod.cn/dns/coredns-dns.html
https://github.com/missdeer/coredns_custom_build
