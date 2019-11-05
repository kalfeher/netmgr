# netmgr
 Ansible role to configure network interfaces to via NetworkManager. Useful for RedHat and CentOS


 Requires the *mv* role.

 ## Example:
 _To change the address of the interface that Ansible uses to connect to the host, use the command below. Note that a restart may still be required._
 `ansible-playbook update_netmgr.yml -e "newaddress=fd01:1:1:1::13/64 ansible_ssh_host=fd01:1:1:1::4" --limit myhost`

 _For DHCP try this command._
 `ansible-playbook update_netmgr.yml -e "interface=enp0s3 ConfType=dhcp4" --limit myhost`


## References:
The role was adapted from here:  https://serverfault.com/questions/666579/recommended-way-to-configure-a-centos-7-network-interface-with-static-settings-v
