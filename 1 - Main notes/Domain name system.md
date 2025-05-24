2025-05-24 10:53

Status: #in-writing
Tags: #applicationlayer #communication #it #udp #technology #ip-address #domain-names

# Domain name system
The domain name system provides a way to translate from human readable names to [[ip addresses]]. The system converts names like google.com to ips like 1.2.3.4. DNS consists of many name severs spread around the world, and it is important to remember that the name servers are implemented at the network edge, and this makes it a part of the [[Application layer|application layer]]. This is to keep the core simple while the edge is more complicated. 

DNS has these services:
- hostname-to-ip translation
- host aliasing
- mail server aliasing
- load distribution (not common anymore i think)

#### Why not centralized
If DNS was centralized there would be one point of failure. And since the service is critical for the internet it cannot go down. It would also mean that there would be way to much traffic to this one place, and that makes it impractical to build a system to handle all the traffic. From some places it would also mean long [[round trip time|rtt]]. This is why a centralized DNS would not work. 

#### How is it decentralized
It is a system of many servers maintained by companies or other organizations that provide the DNS records for their own services. This way the service as a whole can handle trillions of requests at the same time. This approach also makes it more bulletproof and robust. 

### How does the system work
It all starts with the root DNS servers. These are controlled by the [[Internet Corporation for Assigned Names and Numbers|ICANN]] and provide world wide access to the network. These servers will provide the ip addresses of the top level domain servers. This is the servers such as .com, .no, .org and so on. If you want to register a new domain name to your server it would be these ones that you would have to go to. 
After the top level domain is the authoritative domain server. This is the domain server managed by the organization you are looking up. 
It is important to remember the local DNS cache, and that is where domain names are remembered. This way if the local ISP DNS server already knows the ip that corresponds to the domain name it can directly get the ip from the cache. This way we save resources on the DNS infrastructure. 


### DNS records
There are four types of DNS records:
Every record follows this order: (name, value, type, [[time to live|ttl]])

- Type A
	- name is hostname
	- value is ip
- Type NS
	- name is domain name
	- value is hostname for authoritative name server for this domain
- Type CNAME
	- name is alias for real (canonical) name
	- value is the real name
- Type MX
	- value is SMTP mail server for name


## References