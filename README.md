# hmac

HMAC hashing in Lua. 
[HMAC][hmac wiki] algorithm per [RFC 2104].

# Usage Guide
To begin add
 
```lua
local hmac = require'hmac'
```

Compute a hmac hash based on a hash function. Any function that takes a string as single argument works, like `md5.sum`.
`hmac.compute(key, message, hash_function, blocksize[, opad][, ipad]) -> hash, opad, ipad`        

`blocksize` is that of the underlying hash function, i.e. 64 for MD5 and SHA-256, 128 for SHA-384 and SHA-512.

Returns a HMAC function that can be used with a specific hash function.
`hmac.new(hash_function, block_size) -> hmac_function`

`hmac_function(message, key) -> hash`

Compute HMAC-MD5 (requires [md5]).
`hmac.md5(message, key) -> HMAC-MD5 hash`

Compute HMAC-SHA2 (requires [sha2]).
`hmac.sha256(message, key) -> HMAC-SHA256 hash`

`hmac.sha384(message, key) -> HMAC-SHA384 hash`

`hmac.sha512(message, key) -> HMAC-SHA512 hash`

[hmac wiki]:  http://en.wikipedia.org/wiki/HMAC
[RFC 2104]:   http://tools.ietf.org/html/rfc2104
