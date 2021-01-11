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
