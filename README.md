# killswitch-for-openvpn
A killswitch script with autoconnecting function for OpenVPN

## About

This script performs the following:

* It blocks all traffic through your default network interface, except the communication with the VPN IP address, meaning that if the VPN goes down, your traffic will not go through your default interface. 

* It allows full communication through the VPN tunnel interface.

* It reconnects to the VPN tunnel in case it gets disconnected.

## Usage

Give the script execution permission:

```shell
chmod +x killswitch.sh
```

Run the script specifying the full path of your .ovpn file:

```shell
sudo ./killswitch.sh /tmp/vpn.ovpn
```

## Notes

* The script is using tun0 as the VPN tunnel interface, if your OS uses a different one, edit the following line
```shell
TUNNEL=tun0
```

* Make sure your authentication credentials are properly configured within your .ovpn file, so, when the VPN is reconnected, it will not ask you for credentials.
