# Ansible---integration-OEL7-8-9-With-Active-Directory

##Requirements to integrate a new host to AD.

Machine requirements : Setting the hostname and setting up the network files.

Setting the hostname config: `hostnamectl set-hostname SERVER-NAME`

- Setting up the network config file:
    
    1 - Run `“ifdown eth0”` (Disables network interface)
   2 - Edit the file below:
   `/etc/sysconfig/network-scripts/ifcfg-eth0`

  #config that must be done:
  TYPE=Ethernet
  PROXY_METHOD=none
  BROWSER_ONLY=no
  BOOTPROTO=none (set none)
  DEFROUTE=yes
  IPV4_FAILURE_FATAL=no
  IPV6INIT=no (set no)
  IPV6_AUTOCONF=no (set no)
  IPV6_DEFROUTE=no (set no)
  IPV6_FAILURE_FATAL=no (set no)
  NAME=eth0
  UUID= (maintain value)
  DEVICE=eth0
  ONBOOT=yes (set yes)
  IPADDR= 192.168.xx.xx (add this line with IP Address that was reserved to host)
  PREFIX=24 (add this line with subnet mask range)
  DNS1=192.168.xx.xx (add this line with first dns address)
  DNS2=192.168.xx.xx (add this line with second dns address)
  GATEWAY=192.168.xx.xx (add this line with gateway address)



   3 - After finishing the file config, run “ifup eth0” command, to enable the eth0 interface.
