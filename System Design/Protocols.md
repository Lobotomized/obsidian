[[System Design]]

***HTTP*** : Enough said

***Web Sockets*** : Push notifications

***Advanced Message Queuing Protocol*** :

Structure: Producer  (Web Service, Payment system, etc)-> Message Broker -> Consumer (Order Processing, Notification  system).
Purpose  : Ensures delivery. If System A has to communicate with System B and it send a message System B might be down. With message brokers, system B can ask for a message from the broker which acts as a middleman that keeps all the messages.