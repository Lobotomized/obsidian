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


Client -> POST auth/login (with password and username) -> Server 

Server validates the token -> Returns JWT -> Client

