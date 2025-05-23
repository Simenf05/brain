2025-05-23 11:51

Status: #in-writing 
Tags: #http #communication #applicationlayer #it #technology #tcp #www

# Hypertext transfer protocol

### Basis for http
- Http transfers what is called objects (html files, jpeg, etc).
- The http protocol is stateless
- Uses port 80

### Two types
#### HTTP 1.0
HTTP 1.0 is non-persistent which means that it only can transfer one object at a time. In practice this means that for every object that needs to be sent the client and server will have to handshake and establish a connection. This makes the protocol slow and bad for bigger websites. 

#### HTTP 1.1
HTTP 1.1 does mostly the same as 1.0, but allows the connection to stay open for sending of multiple objects. This way when the client first requests the index.html 


## References