DYNDNS_Hetzner
=========

This Playbook updates or creates a DNS Record within your Hetzner DNS managed Zone to a given IP Address. This could be the currently given IP of your Internet Service Provider. If you use a Fritzbox as Internet Modem / Router, you can get your current external IP by using this Playbook [here](https://github.com/thedatabaseme/manage_fritzbox)

Requirements
------------

- Ansible 2.9

You need to have a Hetzner DNS API Key / Token in order to use this Playbook. So your DNS Zone you want to update, must be managed also by Hetzner DNS.
For more informations about the Hetzner DNS Service, have a look [here](https://docs.hetzner.com/dns-console/dns/general/dns-overview/).

Playbook Variables
--------------

- `dns_zone` (Default `mydomain.com`): Top Level Zone you want to have the DynDNS Record managed / created.
- `dyndns_names` (Default `-dyndns`): A list of names of the DynDNS Records you want to get created. Will be added under the Top Level Domain given as `dns_zone`.
- `api_key` (Default `NULL`): The API Key / Token you have to create within the Hetzner DNS Dashboard.
- `external_ip_address` (Default `NULL`): The external IP Address you want to use within the DNS Record. May be your current IP given by your ISP.

Dependencies
------------

Be aware, that this Playbook will run at the localhost (Ansible Controlhost) by default. 

Example Playbook run Command
----------------

An example Playbook Call looks like this. Ofcourse you may want to specify the Variables within your Playbook or within your Inventory:

    - ansible-playbook -i hosts -e "api_key=<HETZNER_DNS_API_KEY> dns_zone=myowndomain.com external_ip_address=92.2.1.118 dyndns_names=cloud" -k -K -u <USERNAME>


Author Information
------------------

This Role is created by P. Haberkern (thedatabaseme)
