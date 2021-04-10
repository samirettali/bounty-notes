# Rate limiting

## Tamper url
Try appending characters to the url or changinging lowercase/uppercase
characters, sometimes rate limiting adopts weird per route logic

## Username based limiting
Sometimes a username based strategy is adopted for rate limiting. As before,
try to add spaces or changing lowercase/uppercase characters in the
email/username

## Captcha
If there is a captcha check if it's actually validated server side

## Correct login
Test if logging in correctly resets the rate limiting

## Bypass using HTTP headers
Try to add these headers to bypass rate limiting:
```
Forwarded-For-IP: 127.0.0.1
Forwarded-For: 127.0.0.1
Forwarded: 127.0.0.1
X-Client-IP: 127.0.0.1
X-Forward-For: 127.0.0.1
X-Forwarded-For-Original: 127.0.0.1
X-Forwarded-For: 127.0.0.1
X-Forwarded-Host: 127.0.0.1
X-Forwarded: 127.0.0.1
X-Forwared-Host: 127.0.0.1
X-Host: 127.0.0.1
X-Originating-IP: 127.0.0.1
X-Remote-Addr: 127.0.0.1
X-Remote-IP: 127.0.0.1
X-Original-Url: 127.0.0.1
X-Custom-IP-Authorization: 127.0.0.1
X-Forwarded-For: 127.0.0.1
X-Rewrite-URL: 127.0.0.1
```
