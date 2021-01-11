# FFUF

## Forward traffic from VPS to local Burp
Connect to the VPS
```
$ ssh -r 8888:localhost:8080 vps
```

Run FFUF
```
$ ffuf -u http://example.com/FUZZ -w ./wordlist -replay-proxy http://127.0.0.1:8888
```
