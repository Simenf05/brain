2025-05-22 13:20

Status: #in-writing 
Tags: #applicationlayer #communication #it #technology #internet #http #dns #www #smtp 

# Application layer

If i want to write an application, then the application layer would abstract away all the complexities of all the other layers. This way making a website is easy because you only need to know how to operate with the http protocol. Even though [[http]] uses [[Transport control protocol|tcp]], [[Internet protocol|ip]] and [[Address resolution protocol|arp]] under the hood. The separation of knowlege needed to make use of the application layer is part of what makes the layers work. From the [[Transport layer]] there is the [[socket]] interface which makes it easy to connect with tcp and make any kind of application on the application layer.

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
The end peers provide service to 

## References
[Jim Kurose video](https://www.youtube.com/watch?v=abeupgK5z48&list=PL1ya5dD_M8uX-BLUF1FEvUNsYWQL5_l0O&index=10)