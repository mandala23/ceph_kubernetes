# infrastructure_deployment

This project contains ansible playbooks to instantiate and configure Ceph & Kubernetes Platform on dedicated Nodes.
 Playbook will deploy following components:

- Requirements for software
- Ceph Stack software
- HaProxy and KeepAlived
- Kubernetes Stack


SELinux must be disabled. Three network interfaces are needed:

 - First one with IP address and GW and a secondary IP address binded to same interface (without GW or static routes). Both of IP on same LAN
 - Second one with IP address for VIP interface used by keepalived. Share the same LAN with the first interface
 - Third interface dedicated to Ceph Replication on another LAN with MTU 9000 (if possible)

