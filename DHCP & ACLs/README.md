###### **Name: DHCP \& Network Isolation**

**Objectives:** To set up DHCP on a router on two networks alongside VLANs \& ACLs to isolate communications.



**Technologies Used:**

* **DHCP:** Configured on the router to provide automatic IP assigning to connected devices - enables scalability to add more devices without manual IP Addressing setup
* **VLANs:** To logically segment the network into two.
* **ACLs:** To prevent traffic travelling across the central router to the adjacent network whilst allowing traffic from other sources, i.e. from the Internet.



NOTE: In regards to the IP Addresses used, I used two IP Addresses for the networks, being "192.168.45.0/24" and "196.172.67.0/24". 

I would prefer to re-configure these IP Addresses next time so that one is "192.168.10.0/24" and the other is "192.168.20.0/24" to showcase proper network segmentation from the same Network ID.



*\[This project is compatible with Cisco Packet Tracer 9.0.1 and above]*

