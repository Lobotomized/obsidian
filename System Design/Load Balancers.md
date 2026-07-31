[[System Design]]

1. **Round Robin** : Just rotates to which server it will send a request. 1st one, 2nd one, 3rd one and than again 1st one etc.
2. **Least Connections** : Finds the server that has the least amount of connections at the moment. Useful for apps with long lasting connections (such as open sockets, sse etc.) where the sessions might have various length.
3. **Least Respsonse Time** : It sends connections to the server with the smallest response time
4. **IP hash load balancer** : It hashes the ip of the client and consistently sends requests to the same server decided depending on the hashed version of the clients.  It might be useful for legacy apps that hold user sessions on the server, for apps that optimize cache per user such as video services or as a prevention of DDOS (limiting the amount of servers that might crash if you have a villain)
5. **Weighted algorithms** : Combination of any of the previous 4 with different weights
6. **Geographical algorithms** : Directing requests to the closest server.
7. **Consistent hashing** : Creates a conceptual circle on which the servers are placed. This is accomplished by representing each link between two servers with particular part of a hash space. Whenever a request comes it is hashed (consistently for particular client) and is sent to the server closest to that hash. In that way if a server fails or a server is added the request will be directed to the new closest hash.


## Examples
***Software*** : NGINX, HAPROXY
**Hardware**: F5 load balancer, Citrix
**Cloud load balancers** : 