Routing protocol for source to destination
- You know the destination when mailing something, but you don't know the specific route it takes

Autonomous systems do this under single administrative organization. 
- Routing between and with other organizations
- Most organizations have 1 autonomous system

##### Relationships
- Customer/provider - USC is small in the context of providing internet to everyone, so they pay to send traffic to Centurylink to reach out to the internet
- Peer-to-peer - 2 networks that are relatively similar size who want to peer into the other. Scientists at both colleges want to be able to exchange traffic. Routers are in the same physical location and they exchange traffic for free but within their own addresses.
### BGP Example
Pakistan tried to block youtube, sent out the announcement to everybody and attracted traffic and blocked for everyone.
### Lessons from BGP Example
BGP was very vulnerable because there was no verification 
#### Solution Techniques
- I'm not going to only remember who owns the prefix and build a topology
- You can check against registries (different regional prefix organization owns a subset of addresses) - and they know who owns each address space
- Cryptographic techniques
- You can look at your announcements and follow the path of traffic, you could find out that you are going through the wrong traffic (unrealistic)

### Defensive Filtering
Works 99 percent of the time but does not work in case where owner is not known

