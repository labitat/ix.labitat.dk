---
#description: "Labitat Internet Exchange"
paige:
  style: |
    #paige-collections,
    #paige-sections,
    #paige-date,
    #paige-reading-time,
    #paige-menu,
    #paige-pages {
      display: none;
    }
    paige-title {
      font-size: 5em;
    }
    #paige_breadcumbs {
      display: none;
    }

title: "LabIX @ BornHack"
---

## Welcome
Hi camping network nerds,

Labitat Internet Exchange (LabIX) will temporarily become a multi-site IX, as we will be present at [BornHack 2023](https://bornhack.dk/). More concretely, we will transport our local peering LAN via our upstream provider to a VLAN the scouting field in Gelsted at BornHack, so you can peer with our members in Labitat and at BornHack.

## Why even do this?
It has now become a tradition for the NOC team at BornHack to ask participant to USE MORE BANDWIDTH. This is of course not about abusing speedtest servers in order to achieve the highest possible throughput or hog the network from other participants, but to use the bandwidth for use-cases that benefits the event, participant or our society.

BornHack usually gets a temporary IPv4 prefix and already got a IPv6 prefix, which is fine for many uses-cases. But you can also choose to run your own little ISP from your village and offer BGP dependent services to other participants (probably costs a beer to the NOC team), or you can use this opportunity to have more on hands experience with the workings of the internet. The IX is totally optional, but it is more fun to announce prefixes and play around, if there are others that can join in on the fun.

## How to connect?
More details will come later, but if you do not already have an ASN and IP resources, now is definitely the time to request some (it takes some time to finalize).

If you plan on joining LabIX at BornHack, please sign up by [creating a pull request on the labix repository](https://github.com/labitat/labix/blob/main/BornHack2023.yml).

## I'm interested! How do learn more about Internet Exchanges
- We will hold a talk on creating LabIX, at BornHack 2023: [Program link](https://bornhack.dk/bornhack-2023/program/labix-creating-an-internet-exchange-in-your-local-hackerspace/).
- The [Network Startup Resource Center](https://learn.nsrc.org/bgp) gives a nice introduction to BGP and Internet Exchanges. [Just give me the slides](http://www.bgp4all.com.au/pfs/_media/workshops/03-ixp-design.pdf), by Phillip Smith, 2021