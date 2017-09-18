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
