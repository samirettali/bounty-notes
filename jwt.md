# JWT

* Always check if the signature is actually verified
* Check for injections in the `kid` header as it's used to retrieve the key before checking the signature
