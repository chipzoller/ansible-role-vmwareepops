Role Name
=========

This role installs and configures the End Point Operations (EpOps) agent on Linux machines and registers them with VMware vRealize Operations Manager (vROps).

Requirements
------------

- Existing vRealize Operations Manager environment online, licensed, and functional.
- Connectivity from the managed/deployed node to the vROps cluster.
- The EpOps RPM file downloaded and stored in the files directory within this role (or otherwise from Ansible).
- The checksum using the SHA1 algorithm of the EpOps agent RPM file.
- A role created and configured inside of vROps with the Manage Agents permission assigned.
- Guest OS which is officially compatible with the EpOps agent.

Role Variables
--------------

All settable variables for this role are found in defaults/main.yml and are as follows.

epops_agent = Name of the agent RPM package.
epops_agent_SHA1 = SHA1 checksum of agent RPM package.
epops_server = vROps server
epops_server_port = vROps server port
epops_server_username = vROps username with Manage Agents permissions
epops_server_pass = Password for epops_server_username account
epops_server_thumbprint = Certificate thumbprint of vROps
epops_runas_root = Indicate if the EpOps agent should run as root.

Please see defaults/main.yml for more complete descriptions and directions on configuring these variables.

Dependencies
------------

None.

Example Playbook
----------------



    - hosts: servers
      roles:
         - chipzoller.vmwareepops

License
-------

MIT

Author Information
------------------

Feel free to contact me on GitHub (https://github.com/chipzoller) or Twitter (@chipzoller). All feedback is most welcome.