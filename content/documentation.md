---
#description: "Labitat Internet Exchange"
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
    paige-title {
      font-size: 5em;
    }
    #paige_breadcumbs {
      display: none;
    }

title: "Documentation"
---

## Linux
### Networking

The following configuration is for an interface named `enp1s0` with the file location `/etc/network/interface.d/enp1s0`. It configures Labicolo IPv4 and IPv6 addresses, but more importantly, it tags VLAN 42 and assigns peering LAN addresses in order for your machine to use the peering LAN for IX related traffic.

Replace interface name corresponding to yours, and replace addresses in \<brackets\> that fits your network interface. Check your `/etc/network/interfaces` file to avoid overlapping interface configurations.

{{< paige/code
    lang="bash"
    options="linenos=true,hl_lines=21" >}}{{% include "content/data/enp1s0" %}}
{{< /paige/code >}}

Reload config with `systemctl restart networking.service`.

### BIRD

The following [BIRD](https://bird.network.cz/) configuration can announce your IPv6 prefixes to your peers, receive a routing table from a transit, and connect to [Route Server 0](/#route-server) via the peering LAN, as highlighted in the example. You need to fill in lines containing \<brackets\> with your own details. The default location for the BIRD configuration is `/etc/bird.conf` or `/etc/bird/bird.conf`. Reload the configuration by opening the BIRD console with `birdc` and use the command `configure soft`.

It is worth noting, that while the route server (and probably your transit) filters for reserved ASNs, reserved prefixes and invalid RPKI ROAs, it is still recommended that you implement these filters yourself. Have a look at the [NLNOG BGP Filter Guide](https://bgpfilterguide.nlnog.net/) for inspiration.

<!-- ToDo: Add Reject on IXP Peering LAN leaks-->
{{< paige/code
    lang="bash"
    options="linenos=true,hl_lines=37 41-46 190-200" >}}{{% include "content/data/bird.conf" %}}
{{< /paige/code >}}
