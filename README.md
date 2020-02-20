# FakeARP daemon

## Intro
This ARP daemon replies to any ARP request for a set of IP addresses with the hardware MAC address of one of the interfaces of the server

## Requirements
On Debian sid:
```sh
$ sudo apt-get install build-essential libdumpnet-dev libevent-dev libpcap-dev
```

## Build
On Debian sid:
```sh
./configure --with-libdumbnet=/usr --with-libevent=/usr
make
```

## Example

Help:
```sh
$ ./arpd -h
Usage: arpd [-d] [-q] [-i interface] [net]
```

For listen and reply only to ARP-requests without VLAN-tags
```sh
sudo ./arpd -d -i enp5s0f4 192.168.1.3 192.168.1.4
```

For listen and reply to ARP-requests with or without VLAN-tag
```sh
sudo ./arpd -d -q -i enp5s0f4 192.168.1.3 192.168.1.4
```
