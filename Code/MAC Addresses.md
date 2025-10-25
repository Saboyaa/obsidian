A `Media Access Control (MAC) address` is a unique identifier assigned to the network interface card (NIC) of a device, allowing it to be recognized on a local network.
Operating at the `Data Link Layer (Layer 2)` of the [[OSI]] model, the MAC address is crucial for communication within a local network segment, ensuring that data reaches the correct physical device.
``` Windows
getmac
```

## Usage
MAC addresses are fundamental for local communication within a [[Network Protocols|LAN]], as they are used to deliver data frames to the correct physical device. When a device sends data, it encapsulates the information in a frame containing the destination MAC address; network switches then use this address to forward the frame to the appropriate port. Additionally, the `Address Resolution Protocol (ARP)` plays a crucial role by mapping IP addresses to MAC addresses, allowing devices to find the MAC address associated with a known IP address within the same network. This mapping is bridging the gap between logical IP addressing and physical hardware addressing within the LAN.