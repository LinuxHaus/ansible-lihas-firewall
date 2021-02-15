# Role Name

Installs and configures firewall-lihas

# Requirements

Uses lihas_common to set up repositiories and lihas_variables to merge the configuration from multiple sources

To run solo:

```
ansible-galaxy install -r requirements.yml
ansible-playbook -i localhost, firewall.yml
```
## Role Variables
Arrays with lines for corresponding the firewall-lihas config files /etc/firewall-lihas.d/interface-IFACENAME/
### %.config.firewall.interface.IFACENAME.comment: []
### %.config.firewall.interface.IFACENAME.dnat
### %.config.firewall.interface.IFACENAME.snat
### %.config.firewall.interface.IFACENAME.mark
### %.config.firewall.interface.IFACENAME.network
### %.config.firewall.interface.IFACENAME.privclients
### bird.ospf.ospf.OSPFNAME.area.AREA.interface


## Integration
* lihas_bird: Add rules for OSPF automatically on OSPF interfaces

## Dependencies

* lihas_common
* lihas_variables

## Example Playbook
```
---
- hosts: '*'
  roles:
    - lihas_firewall
```
