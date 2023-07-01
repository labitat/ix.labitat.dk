---
description: "Labitat Internet Exchange"
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

Labitat Internet Exchange (LabIX) is a non-profit internet exchange created for network research and learning purposes, located in [Labitat (AS205235)](https://as205235.peeringdb.com/), a hackerspace based in Copenhagen, Denmark. The project aims to provide an environment for interested parties to experiment with network routing, in order to gain hands-on experience with the workings of the Internet. LabIX is a community-driven initiative created by students from Technical University of Denmark.

# Status

LabIX is still in its infancy; We are currently setting up the initial hardware/software.

Ongoing:
- ~~ASN allocation~~ AS60247
- ~~IX prefix allocation as specified in [RIPE 733](https://www.ripe.net/publications/docs/ripe-733#61)~~ Acquired, see [route server](#route-server)
- ~~Initial Route Server BIRD config~~ See [repository](https://github.com/Hafpaf/labix) using ARouteServer.
- ~~Choosing BGP filtering strategies~~. ARouteServer has excellent filtering strategies built-in
	- Based on slides from Job Snijders, LACNIC29, 3 May 2018: [slides](https://www.lacnic.net/innovaportal/file/2621/1/lacnic29_peering_tutorial.pdf) (PDF)
	- Based on the [BGP Filter Guide](https://bgpfilterguide.nlnog.net/) from NLNOG  
    - RPKI with routinator
- ~~Setting up peering LAN~~
- Creating automation tool-chain: [repository](https://github.com/labitat/labix)
- ~~Write initial documentation~~ Could always use more documentation

# Route Server

Our route server identifies by [AS60247](https://as60247.peeringdb.com/) and has the following IP addresses in the peering LAN:
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
-   Routes learned through peering network are not allowed to be announced by BGP
-   Connecting via any type of tunnel or VPN/Defragmented MTU is prohibited.

You can be assigned an address within the following subnets:

- 185.0.29.0/24 (only request if needed)
- 2001:7f8:149:1ab::/64

# Cost

Participation in the IX itself is free. However, it is currently required that hardware is placed at [Labicolo](https://labitat.dk/wiki/Labicolo) in Labitat to connect and the cost that entitles, unless otherwise noted.

10/100/1000 BASE-T Ethernet ports are currently available. We do not offer higher port speeds due to power consumption restrictions.

# Software / Hardware

We use [ARouteServer](https://arouteserver.readthedocs.io/) as configuration parser for BIRD, our BGP speaker. It runs on a [Dell Wyse 3030](https://www.parkytowers.me.uk/thin/wyse/3030/). This is due to the availability of the hardware and the low power usage (6W). Our switching hardware is a pre-used Cisco SG300-52.

# Contact details

If you have any questions, contact us at {{< paige/email
    address="labix@labitat.dk"
    text="labix (at) labitat.dk" >}}
or meet us at Labitat in Frederiksberg.


# Thanks

This IX could not have been started up if not for these people:
- Thanks to Jori from the awesome [Freetransit project](https://www.freetransit.ch/), for being our sponsoring LIR and helping in RIPE matters.
- Thanks to Asbjorn (AS207727) for sharing lots of networking knowledge and giving pointers in the right directions.
