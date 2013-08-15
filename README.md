tunneltelnet 0.1
================

This script sets up an SSH tunnel and proxies a telnet session through that tunnel,
to enable a network administrator to reach network devices without having to SSH
into a network management server first. This enables remote scripting and simple
management from a computer outside of the management network.
The script utilizes dig to first resolve DNS names remotely by iterating through a
list of DNS search domains. This is useful when having multiple domains used in the
management network, since the /etc/resolv.conf of the remote server won't be used
by the local dig.

Nonstandard requirements:
- expect
- proxychains >= 4.2.0 (https://github.com/haad/proxychains)

SSH should be set up with public key authrorization to the remote server.
