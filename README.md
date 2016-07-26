# ansible-cjdns

Ansible role for managing CJDNS

The main idea is setting common options for your nodes in the playbook (or vars) and the node-specific options (`privateKey`, `publicKey`, `ipv6`) in inventory. By setting the `connectTo` in the shared settings, one can quickly deploy a cjdns mesh network where every node connects to all the others (the case where a node would connect to itself is handled in the template).

For example usage see playbook.yml.example