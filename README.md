OpenBazaar
=========

[![Build Status](https://api.travis-ci.org/tyler-smith/ansible-role-openbazaar.png)](https://api.travis-ci.org/tyler-smith/ansible-role-openbazaar.png)

OpenBazaar Server Installation Role

Install
----------------

```sh
ansible-galaxy install tyler-smith.openbazaar
```

Role Variables and Defaults
--------------

```yaml
# Whether or not we want a full node or just a seed server
openbazaar_seed: false

# Git URL and version for the server code you want to run
openbazaar_git_url: https://github.com/OpenBazaar/OpenBazaar-Server.git
openbazaar_git_version: master

# Information for the OS user that will run the server
openbazaar_group: openbazaar
openbazaar_user: openbazaar
openbazaar_user_home_directory: /home/openbazaar

# DHT port setting
openbazaar_dht_port: 28467

# The username and password to use when connecting to the API
openbazaar_username: username
openbazaar_password: password

# Any additional flags. Defaults to testnet flag
openbazaar_additional_flags: -t


## Server specific
# Port settings
openbazaar_rest_port: 18469
openbazaar_websocket_port: 18466
openbazaar_heartbeat_port: 18470

# Address to allow API connects from
openbazaar_allowed_ip: 127.0.0.1

# Mainnet seeds
openbazaar_mainnet_seeds:
  - "mainnet_seed2= seed2.openbazaar.org:8080,8b17082a57d648894a5181cb6e1b8a6f5b3b7e1c347c0671abfcd7deb6f105fe"
  - "mainnet_seed3= seed.obcentral.org:8080,f0ff751b27ddaa86a075aa09785c438cd2cebadb8f0f5a7e16f383911322d4ee"

# Testnet seeds
openbazaar_testnet_seeds:
  - "testnet_seed1 = seed.openbazaar.org:8080,5b44be5c18ced1bc9400fe5e79c8ab90204f06bebacc04dd9c70a95eaca6e117"  
  
# LibBitcoin servers
openbazaar_libbitcoin_servers:
  - "mainnet_server1 = tcp://libbitcoin1.openbazaar.org:9091"
  - "mainnet_server3 = tcp://libbitcoin3.openbazaar.org:9091"
  - "mainnet_server5 = tcp://obelisk.airbitz.co:9091"

# LibBitcoin servers (testnet)
openbazaar_libbitcoin_servers_testnet:
  - "testnet_server2 = tcp://libbitcoin2.openbazaar.org:9091,baihZB[vT(dcVCwkhYLAzah<t2gJ>{3@k?+>T&^3"
  - "testnet_server4 = tcp://libbitcoin4.openbazaar.org:9091,<Z&{.=LJSPySefIKgCu99w.L%b^6VvuVp0+pbnOM"


```

Example Playbook
----------------

```yaml
    - hosts: servers
      vars:
        openbazaar_username: myuser
        openbazaar_password: myp@ssw0rD
        openbazaar_additional_flags: ""
      roles:
         - tyler-smith.openbazaar
```

License
-------

[BSD](LICENSE)

Author Information
------------------

Tyler Smith - tylersmith.me@gmail.com
