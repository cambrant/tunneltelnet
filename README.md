tunneltelnet 0.3
================

This script sets up an SSH tunnel and proxies a telnet session through that
tunnel, to enable a network administrator to reach network devices without
having to SSH into a bastion host first. This enables remote scripting and
simple management from a computer outside of the management network.

Tunneltelnet utilizes dig to first resolve DNS names remotely by iterating
through a list of DNS search domains. This is useful when having multiple
domains used in the management network, since the /etc/resolv.conf of the
remote server won't be used by the local dig.

Nonstandard requirements:
- python-pexpect >= 3.1
- python-IPy >= 0.81
- proxychains-ng >= 4.10 (https://github.com/rofl0r/proxychains-ng)

SSH should be set up with passwordless public key authentication to the
remote server, or more preferably with a password protected private key
using an SSH agent.
