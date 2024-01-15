Role Name
=========

This is desisnged to deploy rpc and bootnodes for the ibp program.

Requirements
------------

There are no pre-requisites.

Role Variables
--------------

| Variable      | Definition           | Required |
| ------------- |:-------------:| ------|
| chain_name | Name of the chain | Y | 
|  |
| prometheus_port  |The port Prometheus exporter will expose | |  
| rpc_port | The port the rpc will expose | |  
| ws_port | The port the Web Socket will expose | |     
| libp2p_port | This is the port that the peer 2 peer networking will run on | | 
| node_name | The name that will show up in telemetry | Yes |
| node_key | The private key to set the nodes identity | |
| chain_name | The name of the chain to run | Yes |
| node_p2p_bind_dns | The DNS name to boradcast to the network | |
| local_admin_users | Gives local users administrative privilages | |


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
      - role: ansible/roles/ibp-nodes
        node_name: "kusama-bootnode-STKD-01"
        chain_name: "kusama"
        rpc_port: "9935"
        libp2p_port: "30333"
        prometheus_port: "9615"
        node_role: "boot"
        node_p2p_bind_dns: "kusama-bootnode-STKD-01.bootnodes.stkd.io"
        local_admin_users:
          - greg 
          - steeve
        
      - role: ansible/roles/ibp-nodes
        node_name: "kusama-rpc-STKD-01"
        chain_name: "kusama"
        rpc_port: "9936"
        libp2p_port: "30336"
        prometheus_port: "9616"
        node_role: "rpc"
        local_admin_users:
          - greg 
          - steeve


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
