[[System Design]]

1. **Round Robin** : Just rotates to which server it will send a request. 1st one, 2nd one, 3rd one and than again 1st one etc.
2. **Least Connections** : Finds the server that has the least amount of connections at the moment. Useful for apps with long lasting connections (such as open sockets, sse etc.) where the sessions might have various length.
3. **Least Respsonse Time** : It sends connections to the server with the smallest response time
4. **IP hash load balancer** : It hashes the ip of the client and consistently sends requests to the same server t