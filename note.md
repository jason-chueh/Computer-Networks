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
