# netmgr
 Ansible role to configure network interfaces to via NetworkManager. Useful for RedHat and CentOS

 Requires the *mv* role.

 This role works best with 'Predictable Network Interface Names'.

## Templates and Defaults:
Update the templates with configurations that are meaningful for your environment. The interface 'ID' value is currently the interface name and type of configuration used.
Default interface names should be updated based on your physical or virtual network interface device types.

## Example:
 _To change the address of the interface that Ansible uses to connect to the host, use the command below. Note that a restart may still be required._

 `ansible-playbook update_netmgr.yml -e "newaddress=fd01:1:1:1::13/64 ansible_ssh_host=fd01:1:1:1::4" --limit myhost`

 _For DHCP try this command._

 `ansible-playbook update_netmgr.yml -e "interface=enp0s3 ConfType=dhcp4" --limit myhost`

## requirements.yml
Add the following lines to `requirements.yml` :

~~~
- src: https://github.com/kalfeher/netmgr.git
  name: netmgr
# role 'mv' is listed in the meta/main.yml file as a dependancy.
- src: https://github.com/kalfeher/mv.git
  name: mv
~~~

## References:
The role was adapted from here:  https://serverfault.com/questions/666579/recommended-way-to-configure-a-centos-7-network-interface-with-static-settings-v
