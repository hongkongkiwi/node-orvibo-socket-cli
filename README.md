Orvibo Socket CLI
====================

## Description
A node.js module to control an Orvibo Socket from the command line.

## Install

To install the library globally use

`npm install -g orvibo-socket-cli`

## Controlling from Command line

Note: You must know the ip address and mac of your socket. I suggest you set a static ip assignment on your router.

* `orvibo-socket-cli -i <ip> -m <mac> status` Check Status of Socket
* `orvibo-socket-cli -i <ip> -m <mac> off` Turn off socket
* `orvibo-socket-cli -i <ip> -m <mac> on` Turn on socket
* `orvibo-socket-cli -i <ip> -m <mac> toggle` Toggle the socket

## Controlling OctoPrint

To use the above library in OctoPrint, make sure you install it globally as above. Then add the following to the ~/octoprint/config.yaml

```
system:
  actions:
  - action: printer on
    command: orvibo-cli --uuid SOCKET_MAC_ADDRESS_HERE --action on
    name: Turn on the printer
  - action: printer off
    command: orvibo-cli --uuid SOCKET_MAC_ADDRESS_HERE --action off
    confirm: You are about to turn off the printer.
    name: Turn off the printer
```

That's all there is to it :-)
