# Network Fundamentals

## What is Networking?

- Internet: Network that consists of many small networks within itself
- Devices on a network have two means of identification:
  - IP Adress
  - Media Access Control (MAC) Adress (similar to serial number)
- IP Addresses:
  - IP (Internet Protocol) adress can be used as a way of identifying a host on a network for a period of time, where that IP address can the be associated with another device without the IP address changing
  - Set of number that are divided into four octets, value of each octet will summarize to be the IP address of the device on the network, this number is calculated through a technique known as IP addressing and subnetting
  - IP addresses can change from device to device but cannot be active simultaneously more than once within the same network
  - Follow a set of standards (protocols), these are the backbone of networking and force devices to communicate in the same language
  - Public IP address: Used to identify the device on the internet, given by the Internet Service Provider (ISP) at a monthly fee
  - Private IP address: Used to identify a device amongst other devices
  - Harder to get a public address that isn't already in use with IPv4 (uses a numbering system of 2³² IP addresses), IPv6 is a new iteration of the Internet Protocol (2¹²⁸ IP addresses)
- MAC Addresses:
  - Devices on a network have a physical network interface (microchip board found on the device's motherboard), this network interface is assigned a unique address at the factory it was built at
  - 12 character hexadecimal number split into two's and separated by a colon (e.g. 'a4:c3:f0:85:ac:2d', first 6 characters represent the company that made the network interface, and the last 6 is a unique number)
  - Can be faked or spoofed (spoofing): Occurs when a networked device pretends to identify as another using its MAC address)
