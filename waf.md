# WAF

* Change words casing
* Add `0` in front of port numbers
* Append or prepend spaces, tabs, newline etc
* PHP replaces some characters like `[` with `_` in parameters names, may
  be useful for example if `news_id` is blocked.
* Try `Content-Type: application/x-www-form-urlencoded;/json`

## XSS
* If `<script>` is deleted try `<scr<script>ipt>`
* Bypass any word with: `eval(location.hash.slice(1))` and append `#alert(1)` to the URL
* Transform javascript in symols with [JSFuck](http://www.jsfuck.com/)

### `alert(1)`
* `eval(8680438..toString(30))(1)`
* `Function(/ALERT(1)/.source.toLowerCase())()`

## SSRF
Use these tools to bypass internal hostnames
* [nip.io](http://nip.io)
* [xip.io](http://xip.io/)
* [Welcome to sslip.io](https://sslip.io/)
