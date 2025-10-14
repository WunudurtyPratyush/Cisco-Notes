Troubleshooting intracluster Cisco Unified IP phone

Calls 

The case study in this discusses in detail the call flow between two cisco Unified IP Phones with in a cluster, called intracluster call.

This case study also focuses on cisco unified manager and Cisco unified ip phone initialization, registration and keep alive process. A detailed explanation of an intracluster call flow follows the discussion.

You have two clusters that are named cluster 1 and cluster 2, the two cisco unified communications managers in cluster 1 are called Unified CM3 and Unified CM4, while the two cisco unified communications managers in cluster2 are called unified CM1 and unified CM2.

The traces that are collected for this case study Unified CM1 , which is located in cluster2, as shown in the following figure.

The two cisco unified IP Phones in cluster 2 provide the basis for the call flow. The IP addresses of these two cisco unified IP phones specify 172.16.70.230 (directory number 1000) and 172.16.70.231 (directory number 1001) , respectively.



Procedure:

If you have set the appropriate options in DHCP Server (such as option 66 or option 150) the Cisco unified phone IP Phone sends a request at initialization to the DHCP Server to get an IP address, Domain name System DNS) server address, and TFTP server name or address.  It also gets a default gateway address if you have set these options in the DHCP server  (option 03) 

If DHCP Sends a DNS name of the TFTP Server, you need a DNS server IP address to map the name to an IP address. By pass this step to if the DHCP Server sends the IP address of the TFTP server. In this case study, DHCP Server sent the IP Address of the TFTP Server because DNS was not configured.

If the DHCP server doesn’t include a TFTP Server name, the cisco unified IP Phone uses the default server name.


