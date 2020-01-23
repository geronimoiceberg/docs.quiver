description: arrowd configuration
<!--- END of page meta data -->

# arrowd configuration

The arrow.conf file configures how arrowd operates. You can put the following example file in the proper [default data directory](../troubleshoot/find-data-dir.md). Replace the variables in brackets with the proper data.

!!! Example

    {username} - Any username you would like
    {password} - A secure password
    {internal_ip} - Your `arrowd` host's IP address
    {local_subnet} - Your local subnet (or use localhost if you would only like the server itself to be allowed to connect)
    {max_conn} - any integer, the higher the number the more inbound and outbound arrowd servers can connect
```
# Allow local hosts to connect to RPC with proper auth
rpcuser={username}
rpcpassword={password}
rpcbind={internal_ip}
rpcallowip={local_subnet}
server=1

# Bind to proper address and allow more than the default of 8 connections
bind={internal_ip}
listen=1
maxconnections={max_conn}

# Add seed nodes
addnode=52.90.76.26:7654
addnode=45.77.143.128:7654
addnode=85.15.179.171:7654
addnode=65.100.172.203:7654
addnode=34.204.183.163:7654
```

## Allowing inbound connections
If you want to help support the network by seeding the blockchain to other users, expose the default p2p port `7654/tcp` to the internet.

This varies widely by OS/firewall, but below are examples of the most common Linux firewalls:

### Example FirewallD config

1. Add rule to default zone
    1. `sudo firewall-cmd --permanent --add-port=7654/tcp`
1. Reload firewalld to implement the changes
    1. `sudo firewall-cmd --reload`

### Example IPTables config
1. Add rule to top of default zone
    1. `sudo iptables -I INPUT 1 -p tcp --dport 7654 -m conntrack --ctstate NEW,ESTABLISHED -j ACCEPT`
1. Depending on your specific setup, you should save the firewall rule
    1. `service iptables save` or `/etc/init.d/iptables save`
    
If you are running arrowd on MacOS or Windows, consult Google (or ask in Discord) for more details.