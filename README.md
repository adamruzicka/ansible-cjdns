# ansible-cjdns

Ansible role for managing CJDNS

The main idea is setting common options for your nodes in the playbook (or vars) and the node-specific options (`privateKey`, `publicKey`, `ipv6`) in inventory. By setting the `connectTo` in the shared settings, one can quickly deploy a cjdns mesh network where every node connects to all the others (the case where a node would connect to itself is handled in the template).

For example usage see playbook.yml.example

## Usage with ansible-container

Copy `ansible/main.yml.example` to `ansible/main.yml`, fill in your configuration and edit ports in `ansible/container.yml` to match your configuration. Start it up with `ansible-container build && ansible-container run`. Other containers can then reuse cjdns container's network stack to access the cjdns network by running them with `--net container:$CJDNS_CONTAINER_NAME`.
