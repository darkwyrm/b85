# b85
Golang implementation of the RFC 1924 base85 algorithm, ©2020 Jon Yoder and released under the MIT license.

Several variants of base85 encoding exist. The algorithm used in the official Go base85 package implements ascii85, most famously used in Adobe products. This is not that algorithm.

The variant implemented in RFC 1924 was originally intended for encoding IPv6 addresses. It utilizes the same concepts as other versions, but uses a character set which is friendly toward embedding in source code without the need for escaping. During decoding, whitespace (\n, \r, \t, space) is ignored. A base85-encoded string is 25% larger than the original binary data, which is more efficient than the more-common base64 algorithm.

As of the first release, there are only two methods: `Encode()` and `Decode()`. `Encode()` takes a `[]byte` array and returns a string. `Decode()` returns a `[]byte` array and an error code. The data returned should be considered valid only if `error` is nil.
