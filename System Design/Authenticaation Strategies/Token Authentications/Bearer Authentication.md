[[Authentications]]

Bearer token means : Whoever has this token has access. JWT is the most popular type.

JWT manages to be stateless because instead of lookup the server uses a mathematical proof to validate the identity of the user. 

**1.1. Split the Token:**Separating components.

The server splits the token by its dot (`.`) delimiters into three distinct Base64URL-encoded strings:

- **Header:** Describes the hashing algorithm (e.g., `HS256` or `RS256`).
    
- **Payload:** Contains user identity and claims (e.g., `sub: "user_123"`, `exp: 1718000000`).
    
- **Signature:** The original cryptographic signature generated when the token was created.

**2.2. Recompute the Signature:**Local math check.

The server takes the received **Header** and **Payload** and runs them back through the cryptographic algorithm specified in the header, using the server's own secret key (or public key):

$$\text{Calculated Signature} = \text{HMAC-SHA256}(\text{Header} + "." + \text{Payload}, \text{SecretKey})$$

**3.3. Compare Signatures:**Integrity and origin check.

The server compares its locally calculated signature with the signature attached to the incoming request:

- **If they match:** The token was definitely issued by this server (or an authorized identity provider) and **nobody modified the payload** in transit.
    
- **If they do not match:** Either the secret key was wrong, or an attacker tampered with the payload (e.g., changing `user_123` to `admin`). The request is immediately rejected with a `401 Unauthorized` status
    

**4.4. Validate Expiration and Claims:**Business rule check.

Once signature authenticity is confirmed, the server inspects the claims in the payload without needing a database:

- Is the current time past the `exp` (expiration timestamp)?
    
- Is the `iss` (issuer) recognized?
    
- What is the user's ID (`sub`) or role (`role: "editor"`)?

Client -> POST auth/login (with password and username) -> Server 

Server validates the token -> Returns JWT -> Client

Client -> Token -> If the token is valid success otherwise unsuccess

