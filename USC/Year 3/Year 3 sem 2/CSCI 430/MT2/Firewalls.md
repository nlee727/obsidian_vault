#### Defenses Against Network Mapping and Scanning
NAT routes traffic in and out of the system, also a firewall
- Every firewall server has the ability to map private and public addresses
- IPv4 publicly routable - would try to traverse the internet until it gets back
- Reserved Addresses (private) - 10.0.0.0/8 192.168.0.0/16 - any network can use these addresses and not publicly routable. 
    - Very useful for machines talking within a network
    - If they want to sent outside, they sent it to the NAT box that sends it out to a webpage
        - Request is source address (private)
        - NAT box will rewrite the source address with its own address
        - Source port will be replaced by a random port
- After it goes out to the public server, it comes back to NAT box who reverses the process to change the now destination port 

The big advantage to this
- ALL the sources in the network can just see the outgoing traffic as the NAT box address (1.2.3.4)

###### Outsiders to In
- A has the public IP 
If you want to keep the address private but still want outsiders to communicate with private 
- Advertise the web server A at NAT's address (1.2.3.4 port 80)
- NAT remembers whatever comes for it on port 55 should go to C on port 80
- Clients would have to know which port to use to communicate
    - Do you have a small group of clients, will people always be accessing the website through a click, should you have 

## Firewalls
- If i can bring your firewall down, I can do whatever I want
- Works best for attacks that happen on the network level, not application level
##### Flavors
- Find what's allowed and prohibit everything else
    - Figure out which ports should be open on the server and deny everything else
- Or deny some and allow the rest

- Rules are matched in order and the first match applied
    - Dont make your first rule delete everything, allow 1st 2nd then at the end
#### Packet Filters
- Firewalls that are very simple
    - Dst Port 25 is mail server
    - Rule 1 and Rule 2 traffic get and response
    - Doesn't really protect from outside scanners
        - Attacker can use a low port number by being a super user on a compromised machines and send scans thru rule 3, and replies will come from rule 4
#### Stateful firewall
- Remember the state of the TCP connection and use it in rules
    - EST - established connection, I have a client in by organization in which that initiation changed the state. Only replies on that particular connection can come to me
    - So now, a user who uses a low port number or even the IP address of the web server wouldn't be on an established connection. My machines within any network
### Firewalk:
Attacker wants to determine all the firewall rules to learn what goes through
They can craft packers with traceroute, to see how many packers there are. They will craft the packets to determine the rule
##### Defenses Against firewalking
- If you filter out ICMP time exceeded message the attacker is not going to learn what they are looking for
- FIrewalll proxies
    - The only thing you are achieving is you are limiting the information that the attacker can get. The first approach filters out everything.

### Vulnerability Scanning
- Here you are trying to launch exploits against known vulnerabilities (going further than probing)
The attacker can find existing exploits for the applications and OS.
If you are in charge of the network you should also use these tools and patch them before the attackers can make use of them.
#### Defenses against vulnerability scanning
Force attackers to find 0 day vulnerabilities.
- Closing ports - closing applications that you are not using (Say you migrated your old database server, you want to close that port)

#### At the end of the scanning phase
The attacker may have certain information
### Phase 3: Initial Access
- A vulnerability is some flaw in the system either in design, configuration, etc. That allows an attacker to make the system misbehave
- In the context of intrusions, this is usually a bug in the code that somehow takes user input. An exploit is an input that is designed to take advantage of the vulnerability.

#### Stack Buffer Overflows
Many ways to discover (look at source code, running the application on your gdb seeing where the code crashes, the attacker can look at registers in system memory)

#### Defenses: Stack Overflows
- None is a silver bullet


### Phase 4:
### Phase 5: Maintaining Access
