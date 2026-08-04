Since you need the hashed version of the request for authorization the Client must go through the Challenge / Response flow for initial connection.

The server requires a server-generated secret nonce (number used only once) to build the MD5 hash.

