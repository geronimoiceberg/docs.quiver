description: Configure arrowd
<!--- END of page meta data -->

# Configure arrowd

The `arrow.conf` file configures how arrowd operates. You can copy the following following example into a file and save it in the [default data directory](../troubleshoot/find-data-dir.md). Replace the variables in braces with your own data.

!!! Example

    {username}: Any user name you like  
    {password}: A secure password  
    {internal_ip}: Your arrowd host's IP address  
    {local_subnet}: Your local subnet. If you want only the server to be allowed to connect, use localhost.
    {max_conn}: Any integer. Higher numbers mean more inbound and outbound arrowd servers can connect.

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

## Allow inbound connections

If you want to support the network by seeding the blockchain to other users, expose the default p2p port `7654/tcp` to the internet.

The methods for exposing the `7654/tcp` p2p port depend on your OS and firewall. The following examples show how to expose the `7654/tcp` p2p port in several firewalls.

### Example FirewallD config

1. Add the rule to the default zone.

    ```
    sudo firewall-cmd --permanent --add-port=7654/tcp
    ```

1. Reload firewalld to implement the changes.

    ```
    sudo firewall-cmd --reload
    ```

### Example IPTables config

1. Add the rule to the top of the default zone.

    ```
    sudo iptables -I INPUT 1 -p tcp --dport 7654 -m conntrack --ctstate NEW,ESTABLISHED -j ACCEPT
    ```

1. Depending on your specific setup, save the firewall rule by using one of the following commands: `service iptables save` or `/etc/init.d/iptables save`

If you run arrowd on MacOS or Windows, use Google or [ask questions in the Arrow Discord](https://discord.gg/RdcrR9P) for more details.
