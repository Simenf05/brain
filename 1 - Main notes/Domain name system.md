2025-05-24 10:53

Status: #in-writing
Tags: #applicationlayer #communication #it #udp #technology #ip-address #domain-names

# Domain name system
The domain name system provides a way to translate from human readable names to [[ip addresses]]. The system converts names like google.com to ips like 1.2.3.4. DNS consists of many name severs spread around the world, and it is important to remember that the name servers are implemented at the network edge. This is to keep the core simple while the edge is more complicated. 

DNS has these services:
- hostname-to-ip translation
- host aliasing
- mail server aliasing
- load distribution (not common anymore i think)

#### Why not centralized
If DNS was centralized there would be one point of failure. And since the service is critical for the internet it cannot go down. It would also mean that there would be way to much traffic to this one place, and that makes it impractical to build a system to handle all the traffic. From some places it would also mean long [[round trip time|rtt]]. This is why a centralized DNS would not work. 



## References