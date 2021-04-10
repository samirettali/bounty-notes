# Post scanning

## Firewall bypass
Sometimes firewalls allow all traffic coming from port `53` (DNS), so you can
try to scan a host by making all of your packets originate from port `53`:
```
$ iptables -t nat -A POSTROUTING -d <target_ip> -p tcp -j SNAT --to :53
$ nmap --source-port 53
```

## `nmap` cheatsheet

### Ping scan

Skip port scanning and only ping hosts with ICMP packets:
```
$ nmap -sn <ip>
```

### Scan top ports

You can scan the top 100 ports with `-F` or specify a number yourself:
```
$ nmap --top-ports <n> <ip>
```

### Skip DNS resolution

By default, nmap performs reverse DNS resolution, skip it with:

```
$ nmap -n <ip>
```

--defeat-rst-ratelimit: For TCP scans where you don't care about closed vs filtered, use this option to avoid waiting for rate-limited RST responses from some targets. Since Nmap 7.40, this has been default when you use --open
