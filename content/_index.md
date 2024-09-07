---
description: "Labitat Internet Exchange"
paige:
  style: |
    #paige-collections,
    #paige-sections,
    #paige-date,
    #paige-reading-time,
    paige-menu,
    #paige-toc,
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

LabIX is operational. There is of course work to be done on supporting software like member export schema and automation tool-chain.

If you want to contribute. Please let us know.

## Ongoing: *Updated 2024-09-03*

- Creating automation tool-chain: [repository](https://github.com/labitat/labix)
  - Create IX-F export. [IXPDB entry](https://ixpdb.euro-ix.net/en/ixpdb/ixp/1233/)
    - Expose to website
    - [PeeringDB import](https://www.peeringdb.com/ix/4193) with IX-F schema
  - IX_clients.yml export to website member list
  - Finish website automation
    - Document website automation
  - Document Ansible deployment
- Documentation
  - ~~Write initial documentation~~
  - How to join
  - Address plan
  - VLAN 42
  - Administrator guides
- Setup looking glass
- Move machines in [Labicolo](https://labitat.dk/wiki/Labicolo) to separate switch
  - ~~Some machines moved~~
- 9000 MTU
  - Create separate VLAN for jumbo frames
- Create mailing list

## Already done
- Retiring peering LAN IPv4 prefix and return it to RIPE (185.0.29.1/24)
  - It was an unnecessary cost as we currently have no IPv4 networks being announced.
  - IPv4 peers can use NLRI (IPv4 BFP announcement over IPv6).
- LabIX stickers!
- ~~ASN allocation for Route Server~~ AS60247
- ~~IX prefix allocation as specified in [RIPE 733](https://www.ripe.net/publications/docs/ripe-733#61)~~ Acquired, see [route server](#route-server)
- ~~Initial Route Server BIRD config~~ See [repository](https://github.com/Hafpaf/labix) using ARouteServer.
- ~~BGP filtering strategies~~. [ARouteServer](https://arouteserver.readthedocs.io/) has excellent filtering strategies built-in
	- Based on slides from Job Snijders, LACNIC29, 3 May 2018: [slides](https://www.lacnic.net/innovaportal/file/2621/1/lacnic29_peering_tutorial.pdf) (PDF)
	- Based on the [BGP Filter Guide](https://bgpfilterguide.nlnog.net/) from NLNOG
    - RPKI with routinator
- ~~Setting up peering LAN~~

# Route Server

Our route server identifies by [AS60247](https://as60247.peeringdb.com/) and has the following IP addresses in the peering LAN:
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

We use [ARouteServer](https://arouteserver.readthedocs.io/) as configuration parser for the BGP speaker, BIRD. It runs on a [Dell Wyse 3030](https://www.parkytowers.me.uk/thin/wyse/3030/). This is due to the availability of the hardware and the low power usage (6W). Our switching hardware is a pre-used Cisco SG300-52.

# Presentations

I (Hafnium) presented at BornHack 2023 and CCCamp 2023 about how we set up LabIX and some of the things we learned along the way, like LIR services, RIPE DB and IXP operation. The talks also included some basics of how the networks connects to each other to create the internet. Both talks are similar with minor changes and corrections.

*LabIX: Creating an Internet Exchange in Your Local Hackerspace*
- Chaos Communication Camp 2023: [video](https://media.ccc.de/v/camp2023-57179-labix) ([slides v.2](https://presentation.hafnium.me/labix_presentation_v2.pdf))
- BornHack 2023: [video](https://media.ccc.de/v/bornhack2023-56119-labix-creating-an-int) ([slides v.1](https://presentation.hafnium.me/labix_presentation_v1.pdf))

# Contact details

If you have any questions, contact us at {{< paige/email
    address="labix@labitat.dk"
    text="labix (at) labitat.dk" >}}
or meet us at Labitat in Frederiksberg.

# Thanks

This IX could not have been started up if not for these people:
- Thanks to Jori from the awesome [Freetransit project](https://www.freetransit.ch/), from Openfactory GMBH, for being our sponsoring LIR and helping in RIPE matters.
- Thanks to Asbjorn (AS207727) for sharing lots of networking knowledge and giving pointers in the right directions.
