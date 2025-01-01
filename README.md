# Public vs Private IP Addresses
- have you ever written an application or website hosted on our PC, the moment we move outside your local network we get this error.
- In early 90s if we hooked up our computer to a modem, we would get one IP address, and that is public ip address, and we can be identified on the entire internet with this ip address.
- if we host a node js application on this ip address, everyone can use the ip address on that port and then consume application anywhere on the internet..
- these days we must have multiple devices on local network, we cannot assign public ip addresses for phone, mac and TV, playstation, pretty much every home has a router now..

## Router purposes
- it is the one that connects you to the internet
 explai

ChatGPT: 

### Public vs Private IP Addresses 
**Public IP Address**  
- A **Public IP Address**  is an identifier assigned to your device by your Internet Service Provider (ISP) to make it accessible on the wider internet.
 
- In the early days of the internet (e.g., the 1990s), when connecting a single device (like a computer) to a modem, it would get a **public IP address**  directly. This IP allowed the device to communicate with others across the internet.

- If you hosted an application, such as a Node.js server, on this public IP address, anyone on the internet could access it using that IP and port.
**Private IP Address** 
- With the rise of home networks and the growing number of connected devices (e.g., smartphones, smart TVs, gaming consoles), it became impractical to assign a public IP to every single device.
 
- Instead, routers were introduced to act as intermediaries. 
  - Devices in your home are assigned **private IP addresses**  by the router (e.g., `192.168.x.x` or `10.x.x.x`). These IPs are unique only within your local network.
 
  - The router itself is assigned a single **public IP address**  by your ISP to connect to the internet.


---

**The Role of the Router** 
A router is a device that manages traffic between your local devices and the internet. Its key purposes include:
 
1. **Internet Connection Sharing** :
  - It allows multiple devices to share a single public IP address.
 
  - Uses **NAT (Network Address Translation)**  to map internal private IP addresses to the public IP.
 
2. **Device Communication** :
  - Facilitates communication between devices in the same local network using private IP addresses.
 
3. **Firewall and Security** :
  - Provides basic protection by hiding private IP addresses from the internet.

  - Blocks unwanted incoming connections, reducing exposure to cyber threats.
 
4. **Dynamic IP Assignment** : 
  - Automatically assigns private IPs to devices in the network using **DHCP (Dynamic Host Configuration Protocol)** .


---


### Why You Face Issues When Moving Outside the Local Network 
- there are a lot of ways, the easiest way is port forwarding.
- When you host an application on your computer (using its private IP) within the local network, it is only accessible to other devices connected to the same network.
 
- If you move outside the network:
  - The private IP of your computer is not recognized on the internet.
 
  - To make it accessible, you'd need to configure **port forwarding**  on your router and use the router's public IP for external access.

  ## Port forwarding
  - we create a table in your router, and a lot of router support that, we go to firewall options on your router, we say hey router if you ever receive a request on your public ip on port 8080 please forward it to please forward it somewhere.
  - also its little risky to expose internal network traffic, people can gain access to application and do bad stuff on the machine


  # Security Risks of Port Forwarding
While port forwarding is useful, it can introduce significant security risks if not carefully managed. Here's why:
 
1. **Exposing Internal Services** :
  - Port forwarding essentially exposes your internal network to the outside world. If you open up a port, external users can try to access your application, device, or server.
 
  - **Without proper security** , malicious actors can exploit vulnerabilities in your internal systems.
 
2. **Unprotected Access** : 
  - **Applications**  exposed by port forwarding often lack external-facing security layers (like firewalls, encryption, or authentication).

  - If your web server, for example, is not properly configured, an attacker could gain access to sensitive data or control the server.
 
3. **DDoS and Brute Force Attacks** : 
  - Open ports are also potential targets for **DDoS (Distributed Denial of Service)**  attacks, which can overload your server, or **brute force**  attempts to guess credentials.