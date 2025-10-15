Troubleshooting intracluster Cisco Unified IP phone

Calls 

The case study in this discusses in detail the call flow between two cisco Unified IP Phones with in a cluster, called intracluster call.

This case study also focuses on cisco unified manager and Cisco unified ip phone initialization, registration and keep alive process. A detailed explanation of an intracluster call flow follows the discussion.

You have two clusters that are named cluster 1 and cluster 2, the two cisco unified communications managers in cluster 1 are called Unified CM3 and Unified CM4, while the two cisco unified communications managers in cluster2 are called unified CM1 and unified CM2.

The traces that are collected for this case study Unified CM1 , which is located in cluster2, as shown in the following figure.

The two cisco unified IP Phones in cluster 2 provide the basis for the call flow. The IP addresses of these two cisco unified IP phones specify 172.16.70.230 (directory number 1000) and 172.16.70.231 (directory number 1001) , respectively.



Procedure:

1) If you have set the appropriate options in DHCP Server (such as option 66 or option 150) the Cisco unified phone IP Phone sends a request at initialization to the DHCP Server to get an IP address, Domain name System DNS) server address, and TFTP server name or address.  It also gets a default gateway address if you have set these options in the DHCP server  (option 03) 
2) If the DNS Server is configured, when DHCP Server sends a DNS name of the TFTP server we need a DNS Server IP address to Map the name to an IP Address. Bypass this step if the DHCP Server sends the IP Address of the TFTP server. In this case study, the DHCP Server sent the IP address of the TFTP because DNS Was not configured.
3) If the DHCP server doesn’t include a TFTP Server name, the cisco unified IP Phone uses the default server name.
4) The configuration file (.cnf) gets retrived fron the TFTP Server. All .cnf files have the name SEP<mac_address>.cnf. If this is the first time that the phone is registering with the Cisco Unified Communications Manager (CUCM) , a default file, SEPdeafult.cnf, gets downloaded to the Cisco phone. In this case study the first cisco unified IP Phone uses the IP Address 172.16.70.230 (its MAC address is SEP0010EB001720), and the second cisco Unified IP Phone uses the IP Address 172.16.70.231 (its MAC Address is SEP003094C26105).
5) All .cnf files include the IP Addresses for the Primary and secondary Cisco Unified Communications Managers. The cisco unified IP Phones uses this IP address to contact the primary Cisco unified Communications manager and to register.
6) After the cisco unified IP Phone connects and registers with Cisco unified Coummunications manager, the Cisco Unified Communication Manager tells the Cisco Unified IP Phone which executable version (Called a load ID) to run. If the specified version doesnt match the executing version of the Cisco unified IP phone, the cisco unified IP Phone will request the new executable fromt he TFTP Server and reset automatically.
   

