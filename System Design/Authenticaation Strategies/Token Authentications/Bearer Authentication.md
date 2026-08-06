[[Authentications]]

Bearer token means : Whoever has this token has access. JWT is the most popular type.

JWT manages to be stateless because instead of lookup the server uses a mathematical proof to validate the identity of the user. 




Client -> POST auth/login (with password and username) -> Server 

Server validates the token -> Returns JWT -> Client

