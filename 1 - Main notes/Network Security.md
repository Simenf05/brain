2025-05-22 10:27

Status: #in-writing 
Tags: #communication #internet #cybersecurity #openbsd #openssh #firewall #linux 

# Network Security

### Packet sniffing
Bad actors can get access to packets that travel across the internet with packet sniffers such as wireshark. This is why everything has to be encrypted when sent on the internet. If passwords are not encrypted then they will get stolen. 

### [[Internet protocol|IP]] spoofing
There is also possible to spoof the source of packets on the network. This can be done in order to fake who is sending the packets. To make sure that ips are not spoofed we use authentication methods that guarantee the identity. 

### Denial of service (DOS)
Denial of service is an attack where the attacker launches many requests to the server and overloading the server. This makes the service unusable for any other users and shuts down the application. DDoS is when this is done from multiple hosts at the same time by one bad actor. To make it harder to DDoS we use access restrictions to prevent bad users to access the resources that can compromise the service. 

### Firewalls
Firewalls can be used to mitigate attacks by ensuring certain restrictions on all the traffic in and out of the network. This way DOS attacks can be prevented by blocking users with too many requests. On [[linux]] this can be done by using [[iptables]] or [[ufw]].

## References
[Jim Kurose video](https://www.youtube.com/watch?v=yukwBqSwAkg&list=PL1ya5dD_M8uX-BLUF1FEvUNsYWQL5_l0O&index=6)