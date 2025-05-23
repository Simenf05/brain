2025-05-22 13:20

Status: #in-writing 
Tags: #applicationlayer #communication #it #technology #internet #http #dns #www #smtp 

# Application layer

If i want to write an application, then the application layer would abstract away all the complexities of all the other layers. This way making a website is easy because you only need to know how to operate with the http protocol. Even though [[http]] uses [[Transmission control protocol|tcp]], [[Internet protocol|ip]] and [[Address resolution protocol|arp]] under the hood. The separation of knowlege needed to make use of the application layer is part of what makes the layers work. From the [[Transport layer]] there is the [[sockets|socket]] interface which makes it easy to connect with tcp and make any kind of application on the application layer.

## Client-server paradigm
 The server is a computer with the responsibility of always being on and providing clients with service. The server usually has a static ip address and a domain name resolving at that ip. This way the clients remember the domain names and can easily find the services that they use. For example [google.com](https://google.com), [youtube.com](https://youtube.com) and so on.

Server:
- Is always on 
- Provides service to users
- Permanent ip address
- Often runs [[linux]]

Client:
- Communicates with the server 
- Connected in intervals 
- Often has dynamic ip

## Peer-to-peer paradigm
In peer-to-peer communication the end users are also service providers. This way the load i split up and balanced between different end users. This is commonly used for file sharing with torrents. When the files are big and might be expensive to send from a server will it be better to share the burden in a network of peers. 

## Communication between processes

[[process|Processes]] are programs running on a host, and when we have communication it usually is between processes. With the client-server paradigm the client would be the web browser and the server would be some sort of web server, like [[nginx]]. 
When the communication is between two processes on the same host the communication is called [[inter-process communication]] or IPC for short. When the processes are on different hosts we have to pass messages and this is where we can define the client as the process that reaches out to the other process. The process waiting for a response is the server process. 


### Making a protocol on the application layer
When making a protocol on the application layer, you will have to design what requests and responses the server should use. 


## References
[Jim Kurose video](https://www.youtube.com/watch?v=abeupgK5z48&list=PL1ya5dD_M8uX-BLUF1FEvUNsYWQL5_l0O&index=10)