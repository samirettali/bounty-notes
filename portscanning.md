# Post scanning

## Firewall bypass
Sometimes firewalls allow all traffic coming from port `53` (DNS), so you can
try to scan a host by making all of your packets originate from port `53`:
```
$ iptables -t nat -A POSTROUTING -d <target_ip> -p tcp -j SNAT --to :53
$ nmap --source-port 53
```
