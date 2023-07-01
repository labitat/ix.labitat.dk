---
#description: "Labitat Internet Exchange"
paige:
  style: |
    #paige-collections,
    #paige-sections,
    #paige-date,
    #paige-reading-time,
    paige-menu,
    paige-pages {
      display: none;
    }
    paige-title {
      font-size: 5em;
    }
    #paige_breadcumbs {
      display: none;
    }

title: "Members"
#date: 
---


Members present at [Labicolo](https://labitat.dk/wiki/Labicolo).

{{<table "table table-striped table-bordered">}}
| AS     	| Member                                	| Speed 	| IPv4        	| IPv6                        	|
|--------	|---------------------------------------	|-------	|-------------	|-----------------------------	|
| 60247  	| LabIX Route Servers                   	| 1G    	| 185.0.29.1  	| 2001:7f8:149:1ab::6:0247:1  	|
| 199750 	| Olivia Wenya                          	| 1G    	| 185.0.29.10 	| 2001:7f8:149:1ab::19:9750:1 	|
| 198886 	| Daniel Brasholt                       	| 1G    	| 185.0.29.11 	| 2001:7f8:149:1ab::19:8886:1 	|
| 211153 	| Emil Petersen                         	| 1G    	| 185.0.29.12 	| 2001:7f8:149:1ab::21:1153:1 	|
| 207727 	| Asbjorn Sloth Tonnesen trading as a5n 	| 1G    	| 185.0.29.13 	| 2001:7f8:149:1ab::20:7727:1 	|
| 198275 	| Thomas Flummer                        	| 1G    	| 185.0.29.14 	| 2001:7f8:149:1ab::19:8275:1 	|
| 198186 	| Overkill Consulting ApS               	| 1G    	| 185.0.29.15 	| 2001:7f8:149:1ab::19:8186:1 	|
{{</table>}}

We encourage IX clients to register on PeeringDB.com if not already done so. We use the database for max prefix length and AS-Set filtering. Our PDB entry can be found [here](https://www.peeringdb.com/ix/4193). AS-sets are attempted to be collected from PeeringDB in case it is not available [ix_clients.yml](https://github.com/Hafpaf/labix/blob/main/ix_client.yml). 

The automation tool-chain for exporting members to the IX-F schema (coming soon) and updating PeeringDB currently only includes Route Server clients. This is due to time constrains and as ARouteServer supporting this feature we opted for the working solution. We are aware that forcing IX clients to be route server members is bad practice, which will be worked on as soon as possible.
