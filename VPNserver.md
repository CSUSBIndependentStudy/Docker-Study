## Overview

For my final tutorial, I'll be demonstrating how to setup a VPN server to use with Docker.
This is a very valuable tool, as it allows you to keep the VPN software setup within a 
Docker container versus embedding it inside of the OS itself. There's a whole myriad of 
purposes in using a VPN server, including managing content from a home computer while being
away from home, and you can also use this for routing traffic through a VPN while browsing with
public wifi, ensuring your security against attacks.

## DNS Setup

The first thing we need to do is setup a dynamic DNS service. This enables us to give our server
a permanent address on the Internet. ISPs change your IP address on a consistent basis, but with 
a dynamic DNS, you can point your domain name to the current IP address of your server with the
guarantee that it will not change. My personal favorite is Dynu, but there are a plethora of options
to choose from.

1. Go to www.dynu.com
2. Click "Create Account" in the upper right hand corner.
3. Fill in your information and then check your email for a "verification email."
4. Click on "DDNS Services", then "+ Add".
5. Fill in the Host area with whatever you want, and pick whichever top level you want. This 
isn't an amportant part of the process.

![Screenshot](https://user-images.githubusercontent.com/30271499/30568130-7162fb90-9c88-11e7-9206-04fddec9595a.png)

6. Click "Save". Your DNS is now setup!

## Router Port Forwarding
Next, we need to adjust our home router settings to allow the ports to be forwarded for this service. 
I use an Apple Time Capsule, so here is my settings screen for that. You can easily find out how to 
perform port forwarding for your router by searching Google. The UDP ports 500 and 4500 need to be opened.

![Screenshot](https://user-images.githubusercontent.com/30271499/30568581-cab2fa5e-9c8a-11e7-8877-5802dc1fa299.jpg)

## IPSec VPN Server setup
Here, we'll be using a Docker program to setup the VPN server automatically. Run the following Docker command:

```
docker run --name ipsec-vpn-server --restart=always -p 500:500/udp -p 4500:4500/udp -v /lib/ modules:/lib/modules:ro -d --privileged hwdsl2/ipsec-vpn-server
```
Now go into the logs of the container, and you'll find the Server IP, the IPsec PSK, Username, and Password of 
the VPN server. Make sure to write all of these down as you need them to connect.

Congratulations, now you can use any device to connect to your VPN server, ensuring that you use the credentials
listed inside the container logs, as well as the DOMAIN for your DNS service.
