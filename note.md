
# Introduction to Computer Networks (NTU EE Polly Huang)
## Chap 1: Computer Networks and the Internet
### What is Internet?
Internet is a networking infrastructure that provides services to distributed applications and interconnects billions of computing devices such as thermostats, gaming consoles, home security system and so on, which are called **host** and **end systems**.
![](https://i.imgur.com/Ay5ByPF.png)
**The edge**: connected computing deveices = host = end systems
**Communication links**: fiber, copper, radio, satellite. Transimission rate is measured in  bits/second(bps) or bandwidth
**Routers and link-layer switches**: forward packets(chunks of data) toward their ultimate destinations
**Internet Service Providers (ISPs)**:Each ISP is in itself a network of packet switches and communication links. ISPs provide a variety of types of network access to the end systems, and also be interconnected. The ISPs are loosely hierarchical, but each of them is managed independently.
**Protocals**: control sending, receiving of messages, such as TCP, IP, HTTP. 
**Protocals**: Internet protocals are used among machines rather than human, and govern all communication activity in Internet. Protocals define **format**, **order** of messages sent and received among network entities, and **actions** taken on message tranmission.

---
### The network edge
---
**Clients & Servers**: Hosts are sometimes divided into clients and servers. Clients tend to be PCs, smartphones, and so on while servers tend to be powerful machines that store and distribute data such as web pages, stream video, email etc.
**Client/ server model:** Client host requests, receives service from always-on server. Ex: Web browser/server, Email client/ server
**Peer to peer model:** Minimal or no use of servers. Ex: Skype, Bittorrent

---
### Access Networks
---
Access Networks literally means a network that connect host to the first router.
![](https://i.imgur.com/qOhR9jW.png)
**Residential access nets**(home environment)
**Institutional access nets**(schools, company)
**Mobile access networks**(4G)

---
#### Digital Subscriber Line (DSL):
![](https://i.imgur.com/c4TOa6s.png)

Basic logic: When you make a phone call, the call go through telephone wire and passed to central office by the cable coverd under Taipei city, and then telephone company will make your phone call reach the friend who you calling to.
Later, DSL uses existing telephone infrastructure(wire, cable) to exchange data with central office(DSLAM) which is data network provider.
To be more specific, let's assume that you send an email. The email reaches **DSL modem**(modulator-demodulator) ,converted from **digital form to analog form** and travels through cables to **central office**, which is telephone service provider and often is internet service provider. The **DSLAM** located in the central office will devide the data into two parts: first part will go through telephone network and second part  will be demodulated from analog form back to digital form so that the data can travel on digital network. Vice versa, imagine that your friend sends an email back from both telephone network and digital network. The DSLAM turn them into analog form and go through cables to reach the **splitter**. Splitter then devide it into the telephone part and PC part which will be converted to digital form by modem and reach your PC.

---
#### Cable modem:
Instead using cable TV infrastructure
![](https://i.imgur.com/ZA731R1.png)
Network of cable and fiber attaches homes to ISP router. 
Like DSL, the digital signal is switched to analog signal and vice versa.
**Unlike DSL, which has dedicated access, homes share access to router in HFC(hybrid fiber coax). All the message emerge in one single cable, which leads to the competition of bandwinth, also called multiplexing.** 
**Multiplexing** is a way of sending multiple signals or streams of information over a communications link at the same time in the form of a single, complex signal. 

---
#### Fiber To The Home(FTTH)
![](https://i.imgur.com/ZOS9zvS.png)
FTTH concept is providing an optical fiber path from the CO directly to the home. FTTH has higher internet rates, and fiber also carries television and phone services.

---
#### Ethernet Internet access
![](https://i.imgur.com/7iQCPtu.png)

The most prevalent access technology in corporate, university and home networks.
With Ethernet access, users typically have 100 Mbps or 1 Gbps access to the Ethernet switch, whereas servers may have 1 Gbps or even 10 Gbps access.

---
#### Wireless access networks
**Shared** wireless access networks connects end system to router via base station aka "AP(access point)"

---
#### Home networks
![](https://i.imgur.com/tAP8Yfu.png)
Nowadays, Hybrid access network is used in the household. In the picture, for example, the PC is connected to Ethernet using Ethernet switches, and the switch can also connect to Wifi AP so that laptops can access Ethernet through  wifi. Devices connecting to Internet through different access technology. However, in this example, the access network used by the entire household is cable modem.

---
#### Phsical media

Termanology
* Bit: propagates between transmitter and receiver pairs.
* physical link: what lies between transmitter and receiver.
* guided media: signals propagate in solid media: copper, fiber, coax
* unguided media: signals propagate freely such as radio.

Guided media:
* twisted pair: two insulated copper wires
    * used in 99% of wire connections from telephone to switch
    * Unsheild twisted pair is commonly used for computer networks within a building, for LANs. Data rates range from 10Mbps to 10Gbps.
    * Twisted pair tech is a dominant solution for high-speed LAN networking instead of fiber-optic.
* fiber optic cable: glass fiber carrying light pulses, each pulse a bit
* coaxial cable: two concentric copper conductors; used in HPC
    * Coaxial cable can be used as a guided shared medium

Radio link types:
* terrestrial microwave
    * up to 45mbps
* LAN(e.g. Wifi)
* wide-area(e.g. cellular)
    * 4G cellular: 1+mbps
* satellite
    * 270 msec end-end delay(higher compared to other types)

### The network core
- Hub: layer 1 (physical layer), where it rebroadcast the data to every port that have a device connected to it, which creates security concern because the devices not intened to reach the data now receive it as well. Moreover, it wastes bandwidth. 
- Switch: layer 2 (data link layer), where it routes frames based on MAC addresses(of connected devices). When a data packet is sent to a switch, it's directed to the intended destination port.
- Router: layer 3 (network layer), where it routes packets based on IP addresses. Switch and Hub are used to exchange data within **local network**. To exchange data outside the local network, IP is needed to be recorded. Router plays as the gateway of a network.
![](https://i.imgur.com/gfUFhJX.png)


Mesh of interconnected routers which is highlighted by blue and shaded line.
![](https://i.imgur.com/cCT82EZ.png)
They are two fundamental approaches to moving data through a network of links and switches: **circuit switching** and **packet switching**

Packet: Smaller chunks of data divided from long messages

---
#### circuit switching
When a "call" is made, the resources(cpu, buffer space, bandwidth etc) needed along the transporting path is **reserved**.
* pros
    * Dedicated resources guarantee constant transport rate  
    * The transportations of data won't interfere one another and cause any delay
    * Used in online meeting and streaming.
* cons
    * Network resouces are divided into pieces and allocated to "call". However, if the call didn't send any data in the duration, the resource pieces are wasted.  
There are two approaches to implementing circuit switching: **Frequency-division multiplexing(FDM)** and **Time-division multiplexing(TDM)**
![](https://i.imgur.com/UUMMk1l.png)

**Quiz:**
![](https://i.imgur.com/5e0PPsC.png)
bandwidth: 1.536/24 = 0.064Mbps = 64Kbps  
640,000 bits = 640Kbps  
total time: 640/64 + 0.5 = 10.5 sec

---
#### Packet Switching
Cut data into small packets and tranfer them one at a time. Each packet uses the full link bandwidth. **No idle resources**.  
Network congestion: When aggregate resource demand outnumber the amount available, packets should **wait**( **uncertain delay** might happen!) for link use in a **queue**( there might be a **drop** of data because of limited space of  the queues) in the **router buffers**.  
**Store and Foward**: routers receive complete packet before forwrding to next hop. The more hops you get, the longer transmission delays  

For example:  
L bits per packet  
R bps link transmission rate  
![](https://i.imgur.com/nKELWpr.png)
end to end delay = L/R(from source to router) + L/R(from router to destination)

**Store and Foward**:
1. Why should we divide the data into **small packets** rather than **big packets**?  
For example: L = 7.5Mbits R = 1.5Mbps  
If the whole data is sent without division, the total delay = 3L/R = 15sec  
If the data is broken into 5000 packets, the total delay reduced to 5.002sec because each link works in parallel.
![](https://i.imgur.com/VqHmFh4.png)
2. Why store and foward?  
Every router has a table to record the id of packet and its destination. Router has to check the entire packet first and then send it to appropriate router.
![](https://i.imgur.com/W3ShuU3.png)





#### CS v.s. PS
CS: bandwidth devided into pieces & dedicated allocation & resource reservation  
PS: mixing packets and sharing
PS is more efficient than CS, allowing more users to use network. **Network is based on PS**.
#### Network of networks
End systems connect to Internet via **access ISPs**(Internet Service Providers) and access ISPs must be interconnected so that two hosts in different end system can send packets to each other, resulting network of networks. As time passby, economics drives the evolution.

1. connect each access ISP to every other  
When the internet grow, n extra links are required, which is too expensive to maintain.
![](https://i.imgur.com/DgEj1LU.png)

2. connect each access ISP to one global transit ISP  
![](https://i.imgur.com/fVYbJZB.png)

    Global ISP provides transit service to every access net.  
![](https://i.imgur.com/DwCgChp.png)

    Competitors emerge as the business growing profitable, so here comes numeral global ISPs, which leads to the problem of interconnection of global ISPs. There are two ways: through **IXP(internet exchange point) or peering link**.  
    **IXP** is typically set up by NPO or government act as the third party to maintain the operation of internet to avoid commercial companies' domination.  
![](https://i.imgur.com/r9LMgAg.png)

    As size of access net communities grow, regional net shows up. Regional net earn marginal profit by offering lower price to access net and negotiating with global ISP with lower price. GLobal ISP now only has to face one customer and takes the deal happily.

3. content provider network  
Content provider (e.g., Google, Microsoft, Cloud service company) who has data centers around the world might want to connect access net to their data center, which makes them just as big as global ISPs.  
FYI: Anyone hosting their own content can be content provider(e.g., NTU, Polly's course website) but in smaller scale.
### Delay and loss in packets-switched networks

**Delay**: Aside from transmission delay mentioned above, there is queueing delay in PS networks because packet in the queue has to wait for turn.  
**Drop**: If there are **no free buffers** in the router, arriving packets might be dropped.  

#### Four sources of packet delay
1. Nodal processing  
    a. check bit error  
    b. determine output link by router's algorithm
2. Queueing  
R = link beandwidth(bps)  
L = packet size(bits)  
a = average packet arrival rate  
traffic intensity = $\dfrac{L*a(average\ bits\ arrival\ rate)}{R(outgoing\ traffic\ rate)}$  
La/R ~0: Incoming rate is very low or outgoing rate is very high. Queueing delay is very small.   
La/R =1: delay become large  
La/R >1: more bits coming in than bits going out. When time goes on, newly arrival packet has to wait longer and longer, queueing delay infinite.   
![](https://i.imgur.com/7JKUESZ.png)

3. Transmission  
L/R  
4. Propagation  
d = length of physical link  
s = propagation speed in medium  
propagation delay = d/s
![](https://i.imgur.com/IVQ1VgY.png)

#### Real internet delays and routes
**traceroute program**(or **tracert** in cmd): provides delay
measurement from source to router along end-end
Internet path towards destination. For all i:
* sends three packets that will reach router i on path towards destination
* router i will return packets to sender
* sender times interval between transmission and reply.
![](https://i.imgur.com/SkUfU9m.png)
1. Why the three delay measurements are not the same?
- Because the measurements can be affected by the congestion of router.
2. Why delay measurements to hop#10 are longer than hop#11? 
- Because the path to router might change, the path to 10 can be totally diffent from the path to hop#11. 

**throughput**: rate at which bits transferred between **sender and receiver**.

### Protocal layers, service models
![](https://i.imgur.com/FQ9ZGYx.png)

### Encapsulation
![](https://i.imgur.com/YT8aHFi.png)
**Source:** When the message is passed to the next layer, a header of that certain layer is appended. The header allows the certain layer of source side to communicate with destination side by decyhering the heading.  
**Router:** 
1. From Physical layer to Network layer  
    Each layer inteprets the corresponding header to execute the missions they are assigned, and then passes the remaining message to the next layer.
2. From Network layer to Physical layer  
    Each layer, again, appends new header to message and pass down to the next layer.  

**Destination:**  
Similar to router, layers decypher the corresponding headers and pass the remaining message down.

## Chap2 Application Layer  
### Application architectures
#### Client-server
**Server:**  
**The process that waits to be contacted to begin the session.**
Because server has a **fixed, well-knowned IP addresses** and is **a always-on host**, a client can always contact the server by sending a packet to the server's IP addresses.  
**Client:**  
**The process that initiates the communication.** The hosts who request servers for services. Noted that two clients do not directly communicate with each other with client-server architecture.
#### Peer-to-peer
1. There is no always-on server and arbitrary end systems directly communicate with each others.   
2. Peers request service from other peers and provide service in turn to them.  
3. Peers are intermittenly connected and change IP addresses, leading to complex management  
#### Hybrid of client-server and P2P
Take Skype as an instance:  
There is a centralized server providing service of finding address of remote party. After infromed address, an end system can make a call directly to another peer through P2P system.  

### Socket
A process sends/receives messages to/from **socket**.  
**Socket is the interface between the application layer and transport layer within a host.**
#### Process is **program in execution**
![](https://i.imgur.com/pIuApK8.png)  
There are four sections in a process:
1. Text section - the executable code(fixed sizes)
2. Data section - global variables(fixed sizes)
3. Heap section - memory that is dynamically allocated during program runtime
4. Stack section - temporary data storage when invoking functions(such as function parameters,return addresses and local variables)  

![](https://i.imgur.com/Cvs1nTP.png)
There might be several processes on a single host, so IP address is not enough to identify the process that you sent messages to or receive messages from.  
**Identifier** includes **both IP address and port numbers** associated with process on host.  
There are some well-known services running on some certain prot numbers, such as HTTP server:80 and mail server: 25.  
For example, If you want to send HTTP message to gaia.cs.umass.edu web server, the identifier should be 128.119.245.12(IP address) + 80(port number)  

### Quality of service
1. Data integrity  
    100% reliable data tranfer without any data loss is required by some service, such as web transavtion and file transfer.
2. Timing  
    Low delay is required.
3. Throughput(流通量)  
    Minimum amount of bandwidth is required to be effective.  
    **Elastic** describes those app who do not require throughput.  

![](https://i.imgur.com/flblVAE.png)  

###  Internet transport protocals services  
#### TCP service
1. reliable transport - no data loss
2. flow control - sender won't overwhelm receiver
3. congestion control - confine sender when network overload.
4. **does not provide** - timing, minimum throughput guarantee, security
5. connection-oriented - setup required between server and client processes
#### UDP service
1. unreliable data transfer
2. does not provide - reliablity, flow control, congestion control, timing, minimum throughput guarantee, security.

**The choice between UDP and TCP should be based on the trade-off between reliability and delay.**  
For example, players in PUBG could not suffer high delay in realtime gunfights, so PUBG should choose UDP protocal. However, the trading game like FarmVille might use TCP because every transaction needs to be executed and recorded.
Concurrency is also in practice. Games like RO combine the realtime boss fight and trading, so the concurrency might be the best choice. When fighting, use UDP. Otherwise, use TCP.


### Secure transport
#### Secure TCP

TCP and UDP have no encryption mechanisms, leading the passwords traverse internet in cleartext. Thus, **Secured Socket Layer(SSL)** is needed.
#### SSL
1. provides encrypted TCP connection
    SSL layer is underneath the application layers, the message will go through application layers' protocal, SSL and TCP 
2. ensures data integrity  
    SSL makes sure the message can not be interpretted by the third party.
3. offer end-point authentication  
    SSL can ensure the end system you are connected to is indeed the person you expecting  

#### Public Key System
**Public Key:** Key for a end system that is accessible for everyone.  
**Private Key:** The key that is known only by its owner.  

**Mechanism:** Let's show how a communication between a sender and receiver is encrypted.  First, the sender ask receiver the public key certificate. Then, the sender encrypts the message(MS: master secret) through a function that involves **public key** of receiver as parameter. The encrypted message(EMS: encrypted master secret) is sent to the receiver and receiver decyphers the EMS by a certain function which involves the **private key** as parameter. In this way, the communication is protected because only the receiver has private key and can decrypts the EMS.  
![](https://i.imgur.com/Vq52DJm.png)  
### Web and HTTP
A web page usually consists of one HTML and other objects.  
HTTP(HyperText Tranfer Protocol) defines the structure of these messages and how the client and server exchange the messages.
1. uses TCP as its underlying tranport protocol
2. maintains no past requests of the clients, called as **stateless protocol**.
#### HTTP connections
1. non-persistent HTTP (HTTP 0.9)
    1. At most one object sent over TCP connection,and then the connection is closed
    2. Downloading multiple objects requires multiple connections  
    ![](https://i.imgur.com/rapcvBv.png)  
    ![](https://i.imgur.com/BbCUE5A.png)  
    3. response time
    ![](https://i.imgur.com/0CgCaua.png)

2. persistent HTTP + pipelining (HTTP 1.1)
    1. Multiple objects can be sent over single TCP connection between client and server.
    2. Server leaves connection open after sending response
    3. Client sends all the requests as soon as possible(which is the meaning of pipelining)
    4. Three RTT is required: establishing the connection, downloading the first response item(HTML) and downloading the rest objects(11 pic).
#### Quiz 9
![](https://i.imgur.com/ajjzHXp.png)  
1. 12RTT(TCP connection + request and response)*6
2. 3RTT(TCP connection + downloading HTML + downloading the rest)
3. 7RTT(TCP connection + downloading HTML + one for each new reference object)
4. 4RTT(2 for TCP + HTML; 2 for parallel TCP + new reference object)

#### HTTP request message
![](https://i.imgur.com/OQFxwUy.png)
The request line has three fields: **the method field**(GET, POST, HEAD, PUT and DELETE), **the URL field**(the object that you try to refer to) and the **HTTP version field**.  
The header lines in the figure above include **Host**(specify the host the TCP connection built on)
,**User-Agent**(specify the browser type that is making the request) and **Keep-Alive**(specify how many seconds that the connection should last after receiving last response)  
![](https://i.imgur.com/vtkHyCb.png)

#### The method types
1. GET  
    Request an object inditified in URL field
2. POST
    1. Request an object inditified in URL field
    2. Input is uploaded to server in **entity body**
3. HEAD  
    Ask essential information of an object inditified in URL field.
4. PUT  
    Upload file in entity body to path specified in URL field.
5. DELETE  
    Delete file specified in the URL field.
    
#### HTTP receive message
![](https://i.imgur.com/I8CbogF.png)
The receive message has three sections: **status line, header lines and entity body(data that you request)**.  
**Status line** has three field: **the protocol version, status code and corresponding status message**.  
Header lines:
1. Date: The time that the respond is generated and sent by the server.  
2. Server: The message is generated by apache server  
3. Last modified: The time when the object you downloading last modified.
4. Content length: The number of bytes in the object being sent.  
5. Content type: The object in entity body is HTML text.  

#### cookies
Remind that HTTP is stateless. However, websites might need to keep track of users, and cookie technology is the main solution to it.  
There are four components in cookies:
1. a cookie header line in the HTTP response message:  
    When the request you make comes into website's server, the server **creates a unique identification number and creates an entry in its back-end database indexed by the identification number**. Then, web server sends respond message that includes **"Set-cookie: ++identification number++"** to browser.
2. a cookie file kept on the user's end system and managed by the user's browser:  
    After receiving the respond, the browser adds a line to the cookie file it manages, including the hostname of the server and the identitfication number  
3. a cookie header line in the HTTP request message:  
    If the user continues to browse the website, each time he requests it, the browser consults the cookie file, extract the identification number and put a cookie header line in HTTP request.  
4. a back-end database of the Website server:  
    As it mentioned above, the server creates entry in database indexed by the identification number in cookie headline.Every time the user request the website, the same cookie number will be sent as a header.The server can access the corresponding database entry and record the user's behavior when browsing website and some user's personal info.  

![](https://i.imgur.com/BZ4Ebra.png)

#### local cache
Copies with specified date of recent requested objects are kept in client, somewhere in the local disk. The main goal of the cache system is to reduce traffic between client and server.  
Everytime the client visit the website that was visited before, the request includes:  
```
If- modified-since: <date recorded in cache files>
```
1. If the cache in the local disk is an up-to-date version:  
    The server don't send any object and response:  
    `HTTP/1.0 304 Not Modified`
2. Else:
    The server sends the requested objects in response:  
    `HTTP/1.0 200 OK <data>`
#### web cache
The only difference is that the caches are stored in **proxy server** belonging to the third party, ISP(Internet Service Provider).
The main goal is to satisfy client request without involving origin server.  
```
The browser sends all HTTP request to cache(proxy server)
    if  objects in cache
    {
        cache return objects
        // proxy server acts as server
    }
    else
    {
        request objects from origin server;
        // proxy server acts as client
        return objects to client
    }
         
```
![](https://i.imgur.com/0iYTOuU.png)  
#### why using web cache?
Remind that **queuing delay** for **bottlneck link** might be huge. There are two possible solution:creating fatter access link or web cache.  
The cost of creating fatter access link includes replacing with new cable, grounding work, updating routers, which is very expensive (measured in **millions**).  
In contrast, to implement web cache, an additional server is needed. The cost might be measured in **10Ks**, which is far more cost efficient.

### Email
Three major components
1. user agents
    Called as "mail reader", user agent is used to compose, edit and read mail messages, such as Outlook, Thunderbird, iPhone mail client and Gmail.  
2. mail servers
    1. mailbox: contains incoming messages for user
    2. message queue: outgoing messages that wait to be sent are queuing in mail servers.
    3. play as client when sending mail to other mail server and as server when receiving mail.
3. simple mail transfer protocol(SMTP)
    1. smtp requires always-on servers to receive the mails, so the two layers structure is needed.(That is, we cannot just connect two user agent using smtp because the hosts are not always ready for messages reception)
    ![](https://i.imgur.com/aBz3Dme.png)
    2. Use TCP as the underlying protocol to ensure data integrity during transfer.
    3. SMTP is a **push protocol**(The TCP connection is initiated because sender wants to send objects to receiver), unlike HTTP, which is a **pull protocol**(The TCP connection is initiated because client request objects from server).
#### Email access
![](https://i.imgur.com/gDLJTMI.png)

#### Domain Name System(DNS)
DNS is essentially maintaining the **mapping**(it is a database for sure) between hostname(easier to memorize such as www.google.com) and IP address. Whenever the translation from host name to IP address is needed, the DNS is called. **DNS is the foundation of application layer protocols**.
1. use UDP as underlying protocol
2. is a distributed, hierarchical database:  
    The mappings are distributed across the DNS servers.  

There are three types of DNS servers:
1. Root DNS servers:
    Root name servers provide the IP address to TLD servers.
2. Top-level Domain Servers(TLD):  
    For each of the top-level domain such as com, org, edu, net and gov, there is a corresponding TLD server.
3. Authoritative DNS Server:  
    Every orginization with public access provides their own mapping service through DNS servers.  
![](https://i.imgur.com/8zsC9sn.png)

#### Local DNS server
1. Each **ISP** owns a local DNS server which serves as **proxy server**. When a host makes an DNS query, the local DNS server forwards the query into the DNS hierarchy.  
2. Each time receiving mapping from other DNS servers,the local DNS **can cache the mapping in its local memory**. If the query arrives for the hostname that was cached in local DNS, then the server provides the required IP address.

#### DNS common model
1. iterated query  
The server introduces other server that might know the mapping the host is looking for.
![](https://i.imgur.com/xudFwXI.png)  
2. recursive query  
The query asks the server to obtain the mapping on its behalf.  
cons: might impose heavy load at upper levels of hierarchy.  
![](https://i.imgur.com/7pA1XRO.png)  

#### DNS record
Distributed database storing resource records(RR) that provide hostname-to-IP mappings
```
RR format: (name, value, type, ttl)
```
**TTL(time to live) determines when a resource should be removed from cache.** The meaning of name and value depends on the type:
1. type = A  
    name is hostname, value is IP address
2. type = NS  
    name is domain(ex, foo.com), value is hostname of authoritative name server for this domain
3. type = CNAME  
    Value is the canonical name for a hostname Name.
4. type = MX  
    Value is also the canonical name for a hostname. The only difference is that MX is used to obtain canonical name for **the mail server**, while CNAME is used to obtain canonical name for **other servers**.

#### DNS attack
1. DDoS: attacker sends each root server a deluge of packets to occupy the queue so that server cannot offer service to other users as usual.
However, most of the servers are protected by the packets filter, so the attack deal little damage.
2. DNS poisoning attack: the attacker send bogus replies to DNS server, leading the server caches fake record. However, the attack is hard to implement.  

To wrap this up, DNS is robust against attack.

#### DNS setup
For example: if you just start up a company as NetworkUtopia, and decide to register a domain name: "networkutopia.com". How is it change the  DNS system so that your client can get access to your company online service?  
1. When register domain name, names and IPs of your authoritative servers should be provided.
```
(networkutopia.com, dns1.networkutopia.com, NS)
(dns1.networkutopia.com, 212.212.212.1, A)
```
A NS type record is needed because TLD server has to know the authoritative server's name. A type record then offers the mapping from server's name to IP address.

### Quiz 13
![](https://i.imgur.com/JNP7HH5.png)  
![](https://i.imgur.com/g27wWwQ.png)  

### P2P
The earlier mentioned protocols are all based on client-server model. Next we will visit some P2P based protocols.

#### BitTorrent
The file is divided into equal-size chunks.
The peers in a **torrent**(a group of peers) can download chunks from and upload chunks to one another.
![](https://i.imgur.com/HDy5R6V.png)  
Eachtime a peer joins a torrent, he register the **Tracker** and it sends him a list of current members in torrent so that the new peer can establish connection to each other in the network.   
**The main problem:** if a peer has downloaded the entire file and left, the others can never reach the chunks that the peer takes away.

#### BitTorrent Mechanism
The trackers randomly selects a subset of peers to Amy(the new peer),and hence she can establish **TCP** connection to them. At any given instant of time, Amy has a subset of chunks and know which chunks her neighbors have. 
1. Rarest first  
    From all the chunks she doesn't have, Amy will first request the chunk that is the rarest among the neighbors. This technique can tackle the main problem mentioned above.
2. Tits for tats  
    Amy gives priority to the neighbor that send her data at the highest rate, encouraging reciprocation among peers. In this way, the free riders are marginalized in BitTorrent, and the more you supply, the more data you can get from other peers. 

### Dynamic Adaptive Streaming over HTTP(DASH)

In HTTP Streaming, the videos are stored in server and sent through TCP connection in response to "GET" request.  
However, the shortcoming is that all clients with different available amount of bandwidth receive the same encoding(quality) of the video.  
In DASH, the video is encoded into several versions. The bigger amount of bandwidth you get, the higher quality version of chunks you receive.  
DASH decides:
1. **when** to request chunk  
    prevent buffer starvation or overflow, digestion control
2. **what** encoding rate to request  
    higher quality when more bandwidth available
3. **where** to request chunk  
    The different versions of video are copied to several servers, DASH choose the server that can minimize delay for client. 

### Content Distribution Networks(CDN)

## CH3 Transport Layer

### The difference between Transport Layer and Network Layer
The transport layer protocol provides logical communication **from process to process**, while the network layer provides **from host to host**.  
Noted that there is a large amount of processes running on a host. In household analogy, Ann wants to sent a message to Bill.First, Ann has to **mux** her message and bring it to the mail box of her house. Then, the mailman bring all the messages in the mail box to another house's mailbox. Finally, Bill check his house's mailbox and **demux** the message.  
transport layer protocol = Ann and Bill who mux and demux the messages.  
network layer protocol = postal service between houses.  

### multiplexing and demultiplexing
**multiplexing at sender**: add tronsport header  
**demultiplexing at receiver**: look into header info to deliver received segments to the right socket  
#### connectionless demux
1. UDP socket identified by two tuple:  
    `(destination IP address, destination port number)`  
    Connectionless refers to not knowing the source of message.
2. When host receives UDP segment:  
    directs UDP segment to socket with that port number, leading to IP datagram from different source might be directed to same socket.  
![](https://i.imgur.com/sQg7H6C.png)

#### connection-oriented demux
1. TCP socket identified by 4-tuple:  
    `(source IP address, source port number, destination IP address, destination port number)`
![](https://i.imgur.com/qXbdPwd.png)  

### UDP revisit
#### UDP
1. low delay
    1. connectionless - no connection establishment
    2. no congestion control - as fast as desired
    3. small header size
2. reasonable reliability if needed
    1. can add reliabiliy at application layer
    2. there is a **checksum** value in UDP segment so that the errors in transmitted segment can be detected and hence be tackled with some error recovery techniques.


### Reliable Data Transfer(rdt)
### rdt 1.0
![](https://i.imgur.com/rJoxZ54.png)  
The basic assupmtion of this method is that the transfer is totally reliable and there are no data loss, which is unrealistic in most of the situation  
### rdt 2.0
RDT 2.0 uses "checksum" to detect **bit errors**.
After receiving packet, the receiver will send a message back to indicate whether data loss has happened(NAKs) or not(ACKs). If NAKs is sent back, the sender will then resend the same packet until receiving ACKs.  
There are two states for sender. After being called, the sender sends the packet and transits to another state to wait for receiver's response. The sender can't escape this state until receiving ACK, which is known as **stop-and-wait** If a NAK is received, sender resends packet and keep waiting in the same state.  
![](https://i.imgur.com/n8iklM3.png)  
![](https://i.imgur.com/dwuyAcM.png)  
**what if the feedback from receiver is corrupted?**

### rdt 2.1
To address with the possibilty that the feedback might be corrupted.
How to address:
1. checksum for ACK/NAK  
2. retransmit ACK/NAK if corrupted
3. sender adds sequence number to each packet
4. receiver will ignore duplicate package if there is no bit error and the sequence number is the same as the previous downloaded package. Then receiver keep retransmiting the ACK message until sender stop sending packet(which means the ACK message is not corrupted).  
![](https://i.imgur.com/drPto7z.png)  

**what if the whole packet is missing?**

### rdt 3.0
Inheriting from rdt 2.2, rdt 3.0 still have checksum and sequence number to address the problem of bit error and duplicate packet.  
**In rdt 3.0, sender waits reasonable amount of time for ACK(timeout) and retransmit the packet if no ACK is received until countdown is over.**  
![](https://i.imgur.com/iUjQzhY.png)  
Noted that on the upper right corner, when the packet is corrupted or wrong ACK is received, we used to resend the packet, but we choose to do nothing this time. In fact, waiting for timeout might not be the best solution, and resending the packet immediately sounds fantastic but tradeoff something as the following mentioned.
![](https://i.imgur.com/VzH57X2.png)  
Considering the following case, the ack1 response takes unusual long time, exceeding the timeout, and the sender just resends packet1 as soon as the timeout is over. Then, the delayed ACK1 arrives, making sender think that the packet1 is sent successfully, and hence keeps sending packet0. Because sender just resends the packet1, receiver checks the sequence number and knows that the last ACK1 might loss, and hence resend ACK1 to sender. The sender sending the packet0 ends up receiving ACK1, which is a negative feedback. However, **sender keep ignoring it until timeout**. While sender still waits, the ACK0 arrives.
![](https://i.imgur.com/bSBHZmZ.png)  
If the rdt3.0 works like rdt2.2, sender retransmits immediately when receiving the NAK or corrupted feedback. **There is an extra package0 retransmit comparing the previous example under the ignoring until timeout mechanism, indicating the tradeoff between shortening the communication time and saving bandwidths.**

#### performance of rdt3.0
There are propagation delay and transmission delay that leads to the bad utilization rate of rdt3.0.  
Throughput on 1Gbps link is around 270 kbps(not even enough for streaming)  
The solution for increasing utilization is pipelining, which sends a lot of packages consecutively.  
![](https://i.imgur.com/751AUHF.png)
### Pipelining
Send multiple packages at the same time, allowing "in flight" packages.
However, the pipelining might post challenge to existed mechanism.
1. Sequence number  
    Sequence number is used to identify different packages. With the packets number increasing, it is necessary to increase the sequence number.
2. Buffering at receiver and sender  
    Noted that when a packet is sent, the sender/receiver has to wait for the ACKs. If the packet is corrupted or timeout, they have to **resend** the packet. Hence, there must be a buffer storing all the in flight packets so that they can be resent when needed.
### Go-Back N(GBN)


### GBN V.S. SR


|     | Go-Back N | Selective Repeat |
| --- | --------- | ---------------- |
|   Resend  |   Resend all the packet with previous sequence number| Resend packet for which ACK not received             |
|   Buffer  | Receiver don't need to buffer the received pakets |  Receiver has to buffer the **out of order** packets, waiting for eventually in-order delivery to upper layer      |
|     |           |                  |
|     | Text      | Text             |

### Quiz 22
![](https://i.imgur.com/aPc06Nj.png)  
1. Seletive repeat. When sending error happens, BGN has to resend all of the previous packets, which is bandwidth-consuming


### TCP
In rdt, we count the data by "packet number", but in TCP, we count the data by "bytes".
![](https://hackmd.io/_uploads/B1YJrKoEh.png)


![](https://hackmd.io/_uploads/HJgLdOsN2.png)  

![](https://hackmd.io/_uploads/H1hNuuiVn.png)  
1. t1: Arrival of in-order segment with expected seqence number & no corruption & not filling the gap of sequence order & there is no pending ACK  
    1. TCP receiver delays ACK, starting timer for next segment.
    2. Set pending value to true, meaning that there is one ACK waited to be sent.
2. t2: not filling the gap of sequence order & there is a pending ACK.  
    1. Send the ACK of the oldest received packet immediately to acknowledge the sender that both of the packets are received.
    2. Remove the timer since there is no pending ACK now.
3. t3: Arrival of out-order segment filling the gap of sequence order.  
    1. if gap is partially filled, send the packet with the sequence number start at current the lowest end of the gap immediately. If the gap is completely filled, send the next expected sequence number.


4. t4: Else, send the **duplicated ACK** and remove the corresponding timer.


How the delayed ACK work?  
When the sender receives the delayed ACK, he can be sure that the previous sent packets are ACKed althought he didn't receive the respective ACK because if the first packet is missing through the tranfer and the second packet arrives, the receiver consider the packet out of order and will send back **duplicated ACK** instead of sending back the ACK corresponding to the second packet. Hence, the only explanation for the sender receiving the ACK number higher than some of the unACKed packet is that the previous packets are also acknowledged by the receiver.

Why not delayed all the ACK?  
Extra buffer space for storing the delayed ACK is needed, which forms a trade-off between saving bandwidth by reducing the ACK package sent and saving memory space, and it might not saving the bandwith as well because during the waiting time, the sender might resend the packets.

#### TCP fast retransmit
If the sender received three duplicate ACKs for same data, then the sender will ignore the timeout interval and resend the unACKed segment with smallest sequence number(very likely the lost segment)  
**This mechanism can address with the relatively long process of time-out period.**
![](https://hackmd.io/_uploads/HJUsk624h.png)  

#### TCP three way handshake to establish connection
To establish TCP connection, three packets are needed to sent between sender and receiver, hence the mechanism is referred to three-way handshake.
1. The sender send IP datagram with a TCP segment where a SYN flag set to 1 to server. The sequence number is randomly chose by the sender so that the connection will not be interjected by hacker.
2. Onece the receiver decides to establish connection, it sends back an TCP segment with acknowledgement number set to **client_initial_sequence_number + 1**, distinguished itself from other fake response, and also randomly chooses a sequence number(server_isn).
3. On receiving the SYNACK data, the sender start sending data to server by **setting the acknowlegment number to server_isn + 1**.

![](https://hackmd.io/_uploads/BJsqvah4h.png)  


### TCP flow control
![](https://hackmd.io/_uploads/rJEz_xIS2.png)  
The packets extracted by the receivers do not go directly to the application. Instead, they are stored in the TCP receiver buffer. However, if the rate of application removing data from buffer lower than the TCP receiver extracting the packets to buffer, the buffer space will be more and more occupied, leading to the subsequent data drop. Hence, the flow control is needed to avoid buffer space overflow.  
Receiver inform the free buffer space to the sender by the **rwnd value** in TCP header. The sender limits amount of unACKed data to the rwnd correspondingly, guaranteeing that buffer will not overflow.

### TCP congestion control algorithm
#### Congestion control approaches
1. End-to-end(used by TCP):  
    End-systems observes packet loss(duplicate ACKs or timeout retransmission), infering explicit rate/bandwidth by trying and failing(speed up and slow down).
2. Network-assisted:  
    Routers observe the queue size and free buffer space directly, being able to tell the explicit rate. If sender sends at the same rate that routers indicates, congestion issues are solved.
#### TCP AIMD(Additive Increase & Multiplicative Decrease)
1. AI: Increase the congestion window size(cwnd) by one every runtime.
2. MD: Cut the window size in half after loss occurs.

By limiting congestion window size, the sender can limit transmission rate. CWND decides the number of package-in-flight.

#### TCP slow start
At the begining of TCP connection, cwnd increase exponentially(double it every runtime!) **until first loss event.**  
The slow start refers to the fact the cwnd initialized as 1, but the cwnd ramps up exponentially.  

#### TCP reacting to losses
There are different ways to deal with loss detections:
1. Fast retransmit:  
    After receiving three duplicate ACKs, the sender will retransmit immediately. TCP RENO addresses this kind of loss by AIMD.
2. Timeout:  
    When timeout occurs, cwnd is cut down to one and **grows exponentially to a threshold**, then grows linearly after reaching threshold. Noted that threshold is open to adjustments.

3. TCP Tahoe:  
    Always set the cwnd to 1 regardless of the type of loss detection.
![](https://hackmd.io/_uploads/ryrkQil82.png)

## Network Layer
### Overview
Network layer is responsible for the packet tranportation from one host to another, going through the routers and finally reach the receiveing host. Noted that every router is running the network layer protocols as well.  

### Network layer functions
1. Routing / Control plane  
    Decide the source to destination of the packets, underlying some routing algorithms. There are two control plane approaches: 
    1. traditional routing algo:  
        The routing algo is runned by the router itself.   
    2. software defined networking(SDN approach):  
        The routing algo is outsourced to some powerful servers to do the calculation remotely.  
2. Forwarding / Data plane  
    After recieving the forwarding table, network layer should move packets from router input to specific router output. The router first checks the table, matching the heading of packets and decides the output port for the packet.

#### The traditional routing approach
![](https://hackmd.io/_uploads/rJMMZOnL3.png)  
The routers contain both routing and forwarding approaches.

#### Software Defined Networking approach(SDN)
![](https://hackmd.io/_uploads/HJOezu2L2.png)  
The remote controller in the remote server executes the routing algo. Because the RC dont know the information about routers, the control agent(CA) is needed as intermidiates. The CA passes necessary info to the CA, and after receiving forwarding table from CA, it then sends the table to the router.  

### Switching Fabric

Traditionally, the speed of packets sending is limited by memory bandwidth
    
### IP fragmentation
The MTU(maximum transmission unit) of every link might be different because each link may use disparate link layer protocols. In order to tranfer the IP datagram successfully throughout the route, it is necessary to fragment the IP datagram into small fragments.
The IPv4 use length, ID, flag, offset to divide and reassemble the fragmented datagram.  
![](https://hackmd.io/_uploads/Hkut7xiv3.png)
**Noted that the reassembly happens only on the end system.**
#### Reassembly of IP fragment
![](https://hackmd.io/_uploads/S1TyElswh.png)
1. ID iditentify the same IP datagram that the smaller datagram belongs to.
2. Flag indicates if this is the last piece of IP datagram: 1 means false while 0 means true.
3. The offset number is the bit position of the original and undivided datagram. The reassembly can be easily done by sort the smaller datagrams by the offset number in numarical order, and then merge all the datagrams.