Since you need the hashed version of the request for authorization the Client must go through the Challenge / Response flow for initial connection.

The server requires a server-generated secret nonce (number used only once) to build the hash.

**1.Initial Request (Unauthenticated):**

The client requests the resource without authentication headers.

**2.Server Challenge:**

The server rejects the request with `401 Unauthorized` and returns a `WWW-Authenticate: Digest` header containing a fresh **nonce** string, realm, and supported hash algorithm (e.g., MD5 or SHA-256).

**3.Client Hash Calculation:**

The client hashes the username, password, realm, HTTP method, URI, and the server's nonce (plus a client-generated `cnonce` to prevent replay attacks):

$$\text{Response Hash} = \text{Hash}(\text{Hash}(U:R:P) : \text{nonce} : \text{nc} : \text{cnonce} : \text{qop} : \text{Hash}(M:\text{uri}))$$

**4.Authenticated Request:**

The client re-sends the request with the `Authorization: Digest ...` header containing the computed `response` hash alongside the `nonce`. The server computes the same formula locally; if hashes match, access is granted.