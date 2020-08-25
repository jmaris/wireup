# wireup - a simple wireguard configurator in bash

## intro
Want to connect a couple of computers together with a wireguard server? This tool makes it easy as ssh!
Set up Wireguard networks with up to 253 clients automagically (dev was too lazy to make it more complex)

## usage

- Initialise a wireguard server on 51.52.53.54, with interface name vpn1, using the 10.0.0. range and running on port 51820.
```
ssh youruser@51.52.53.54
wget https://raw.githubusercontent.com/jmaris/wireup/master/wireup
sudo mv wireup /usr/bin/wireup
sudo wireup server init 51.52.53.54 vpn1 10.0.0. 51820
```
- From any potential client, adds peer to the server and returns a client config ready for use:
```
https://raw.githubusercontent.com/jmaris/wireup/master/wireup
./wireup client clientname youruser@51.52.53.53
```

## caveats
- as previously mentioned, this won't handle jumps in IP range because it was never designed to be used for lots of clients. it is for small networks.
- the user on the remote server must have sudo access.
