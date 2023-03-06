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
---
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
mesh of interconnected routers
#### circuit switches