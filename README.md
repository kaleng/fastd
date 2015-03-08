fastd
=========

This role installs and configures fastd, the Fast and Secure Tunnelling Daemon.

Role Variables
--------------

See: http://fastd.readthedocs.org/en/v16/manual/config.html

    fastd_bind:
    - address: ipv4 / ipv6 address
      port: Port (1-65535)
      interface: interface to bind to
    fastd_drop_capabilities: (default: yes)
    fastd_forward: (default: no)
    fastd_hide_ip: (default: yes)
    fastd_hide_mac: (default: yes)
    fastd_interface: name of the VPN-interface
    fastd_syslog_level: (default: info)
    fastd_methods: see http://fastd.readthedocs.org/en/v16/manual/methods.html
    - 'salsa2012+umac' (default)
    fastd_mode: (default: tap)
    fastd_mtu: (default: 1426)
    fastd_on_pre_up:
      mode: sync/async (default: sync)
      command:
    fastd_on_up:
      mode: sync/async (default: sync)
      command:
    fastd_on_down:
      mode: sync/async (default: sync)
      command:
    fastd_on_post_down:
      mode: sync/async (default: sync)
      command:
    fastd_on_connect:
      mode: sync/async (default: async)
      command:
    fastd_on_establish:
      mode: sync/async (default: async)
      command:
    fastd_on_disestablish:
      mode: sync/async (default: async)
      command:
    fastd_on_verify:
      mode: sync/async (default: async)
      command:
    fastd_pmtu: (default: auto)
    fastd_peers:
      [name]:
        peers_dir: '[dirname]'
        peers_limit: maximum number of peers to connect to
    fastd_repository_key: (default: '6664E7BDA6B669881EC52E7516EF3F64CB201D9C')
    fastd_secret: fastd private key (mandatory)
    fastd_secure_handshakes: (default: yes)
    fastd_status_socket: (default: '/tmp/fastd_status')
    pgp_keyserver: (default: 'pool.sks-keyservers.net')

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars:
        fastd_bind:
        - address: '0.0.0.0'
          port: 10000
        fastd_interface: 'fastd-vpn'
        fastd_secret: '[key]'
      roles:
      - fastd

License
-------

GPLv3

