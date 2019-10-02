# OpenVPN setup in docker, easy to run

## How to use

### Initialize the configuration files and certificates

```bash
docker-compose run --rm openvpn ovpn_genconfig -u udp://VPN.SERVERNAME.COM
docker-compose run --rm openvpn ovpn_initpki
```

You can edit server name as Your IP server.

### Start OpenVPN server process

``docker-compose up -d``

### Generate a client certificate

```bash
export CLIENTNAME="your_client_name"
# with a passphrase (recommended)
docker-compose run --rm openvpn easyrsa build-client-full $CLIENTNAME
# without a passphrase (not recommended)
docker-compose run --rm openvpn easyrsa build-client-full $CLIENTNAME nopass
```

After that, you can this command to retrieve the client configuration with embedded certificates:

``docker-compose run --rm openvpn ovpn_getclient $CLIENTNAME > $CLIENTNAME.ovpn``

After above command, it create for you a file is $CLIENTNAME.ovpn in current directory, you can use it to import a VPN Connection.

Good luck to you!
