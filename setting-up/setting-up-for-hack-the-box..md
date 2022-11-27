# Setting up for hack the box.

Always connect through a separate box! I'd recommend a small hetzner cloud instance, but this way you don't expose your own machine, and you don't have to worry about mac or windows specifics when exploiting.&#x20;

## Getting OpenVPN set up

Don't fall for the oldest trick in the book!&#x20;

To set up openvpn on ubuntu you want the OSS package, not the openvpn3 package.

Simply use `sudo apt install openvpn` and then run your downloaded openvpn config with

`sudo openvpn lab_<username>.ovpn`

``

## Setting up a socks5 proxy&#x20;

If you want to access any remote boxes or websites from your own machine you must set up a socks proxy.

The below command will set up a proxy through the ssh tunnel. Add localhost 1337 to your proxy settings to access it.&#x20;

```
ssh -D 1337 <hetzner-box> 
```

To support funkier protocols you may to use proxy chains.&#x20;
