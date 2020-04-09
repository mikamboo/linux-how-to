# Interfaces

## Network interfaces

Show network interfaces

```bash
$ ifconfig
```

Restart network interfaces

```bash
# Restart network manager
$ sudo service network-manager restart

# Restart a net interface
$ ifconfig eth0 down && ifconfig eth0 up

# To renew or release an IP address for the eth0 interface
$ sudo dhclient -r eth0
```

