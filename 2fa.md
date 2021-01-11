# 2FA

## Bypasses

### `..`
Try to use `..` as token because sometimes apps interprets status code 200 as
successful

### Rate limiting
Test if there is no rate limit on 2FA in order to take over accounts

### Password reset 
Just try to reset the password, sometimes you get logged in directly

### Shared tokens
Try to use another user's token as yours

### Token reuse
As easy as it sounds, try to reuse an old token

### Old version
If your login is in `/v3/auth/login`, try older version of the API, maybe 2FA
is not present
