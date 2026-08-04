
Client -> Login Credentials -> Server -> Creates Session -> Session Store 

Session Store -> Session ID -> Server -> Set Session cookie -> Client

Client -> Request with Cookie -> Server -> Lookup Session -> Session Store

Session Store -> User Data -> Server -> Auth response -> Client



***Weaknesses*** can't scale easily since the server has to be stateful.