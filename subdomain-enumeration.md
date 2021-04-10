# Subdomain enumeration

* Search for copyright strings on Google to find domains

## Virtual host
When a subdomain is not resolved, try using it as a virtual host with the main
domain

## SAN
List subject alternative names:

```bash
$ openssl s_client -connect example.com:443 | \
	openssl x509 -noout -text | \
	grep -o 'DNS:[a-z\.]*,'
```
