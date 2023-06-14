---
description: "Labitat Internet Exachange"
paige:
  style: |
    #paige-collections,
    #paige-sections,
    #paige-date,
    #paige-reading-time,
    paige-menu,
    #paige-pages {
      display: none;
    }
    #paige-title {
      font-size: 5em;
    }

title: "LabIX"
date: 
---


# What is this?

Labitat Internet Exchange (LabIX) is a non-profit internet exchange created for network research and learning purposes, located in [Labitat (AS205235)](https://www.peeringdb.com/net/23277), a hackerspace based in Copenhagen, Denmark. The project aims to provide an environment for interested parties to experiment with network routing, in order to gain hands-on experience with the workings of the Internet. LabIX is a community-driven initiative created by students from Technical University of Denmark.

# Status

LabIX is still in its infancy; We are currently setting up the initial hardware/software.

Ongoing:
- ~~ASN allocation~~ AS60247
- ~~IX prefix allocation as specified in [RIPE 733](https://www.ripe.net/publications/docs/ripe-733#61)~~ Acquired, see [route server](#route-server)
- Initial Route Server BIRD config
- Choosing BGP filtering strategies
	- Based on slides from Job Snijders, LACNIC29, 3 May 2018: [slides](https://www.lacnic.net/innovaportal/file/2621/1/lacnic29_peering_tutorial.pdf) (PDF)
	- Based on the [BGP Filter Guide](https://bgpfilterguide.nlnog.net/) from NLNOG  
- Setting Up peering LAN
- Creating automation toolchain: [repo](https://github.com/Hafpaf/labix)

# Route Server

Our route server identifies by [AS60247](https://as60247.peeringdb.com/) and has the following IP adresses for the peering LAN: 
- IPv4: 185.0.29.1
- IPv6: 2001:7f8:149:1ab::6:0247:1

# Peering Policy

Our peering policy is currently based on [LocIX's peering policy](https://locix.online/technical.html).

Following policy guidelines are mandatory for the safety of our peering platform. Violations will lead to disabling of ports and termination of the peering connection.

-   Allowed Ethernet frames:
	- 0x0800 - IPv4
	- 0x0806 - ARP
	- 0x86dd - IPv6
- Proxy ARP, OSPF, DHCP, STP/RSTP/VSTP with any kind of CDP/ZEROTIER are not allowed
-   MAC-addresses are filtered per port
-   Routes learnt through peering network are not allowed to be announced by BGP
-   Connecting via any type of tunnel or VPN/Defragmented MTU is prohibited.

You will be assigned an address within the following subnets:

- 185.0.29.0/24
- 2001:7f8:149::/48

# Cost

Participation in the IX is free. It is a possibility to place hardware at [Labocolo](https://labitat.dk/wiki/Labicolo) in Labitat to connect.

10/100/1000 BASE-T Ethernet ports are currently available. We do not offer higher port speeds due to power consumption restrictions.

# Software / Hardware

We use arouteserver as configuration parser and BIRD as BGP speaker on a [Dell Wyse 3030](https://www.parkytowers.me.uk/thin/wyse/3030/). This is due to the availability of the hardware and the low power usage (6W). Our switching hardware is an old Cisco SG300-52.

# Contact details

If you have any questions, contact us at {{< paige/email
    address="labix@labitat.dk"
    text="labix (at) labitat.dk" >}}
or meet us at Labitat in Frederiksberg.


# Thanks

Special thanks to Jori from the awesome [Freetransit project](https://www.freetransit.ch/), for being our sponsoring LIR and helping in RIPE matters.
