The Clients asks for a resource on an endpoint and receives  401 Unautorized.
So in the upcoming request the Client again sends request to the same endpoint but this time with Authentication header that has Base64 encoded username and password. 
Than if the password and username match the server returns 200 + the resource data otherwise it says 401 Unautorized.