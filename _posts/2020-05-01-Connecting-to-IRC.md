---
layout: post
title: 'Connecting to IRC'
---

![IRC](/_img/irc.png)
## Internet Relay Chat
### 1. What is it?

Internet Relay Chat abbreviated as IRC which is just another application layer protocol like FTP, SMTP, DHCP, etc. It is mainly use for communicating in the network in the form of text messages. Architecturally IRC is a client/server model which consists of IRC server and IRC clients. IRC server accepts and relay messages to the users who are connected via IRC clients. There are numerous IRC clients availabe in the internet which we will be describing shortly. IRC consists of numerous networks and which is further divided into channels. Channels are also called rooms where user of particular interest can gather and exchange messages. Each of the channels starts with a hashtag '#'. 

### 2. Popular clients

Over the years, different IRC clients has emerged claiming to be best with performance and reliability. Some of the popular IRC clients are given below:
- HexChat
- Polari
- Weechat
- Irssi
- Konversation
- Smuxi

### 3. Installation 

Installation is pretty simple since every linux distribution has packaged it in its standard pacage manager. 

- Ubuntu

``` apt-get update && apt-get install -y weechat ``` 

- Fedora

``` dnf uopdate && dnf install weechat ``` 

- CentOS

``` yum update && yum install weechat ``` 

- Arch Linux

``` sudo pacman -Syy && pacman -S weechat ``` 

Now the weechat is installed and you can run it with the binary ``` weechat ``` rightaway.

### 4. Connecting to the servers

For the demonstration purpose I am using Weechat client for connecting to the servers. Weechat is a command line IRC client which is designed to be light and fast. It is a opensource software which is released under the terms of the GNU General Public License 3. 

#### Connecting to OFTC network

- Create a server 

``` /server add oftc irc.oftc.net/6697 -ssl --autoconnect ``` 

Here 6697 is a port number for the SSL connection. You can also use other port for non-ssl connection. 

- Connect to the server

``` /connect oftc ``` 

After this, you may join the different chat rooms available over the internet. For e.g. To join the Linux Kernel Newbies community, simpley follow the below given step. 
    
``` /join #kernelnewbies ``` 

#### Connecting to freenode newtork

- Create a server 

``` /server add freenode irc.freenode.net/6697 -ssl --autoconnect ``` 

- Connect to the server

``` /connect freenode ``` 

After this, you may join the different chat rooms available over the internet. For e.g. To join the Linux Device Driver community, simpley follow the below given step. 

- Join the network

``` /join #dri-devel ``` 

### 5. Connecting through the SSH Tunnel

Sometime your Internet Service Provider blocks your connection to the IRC server because of security concerns. What I meant is IRC channel expose your IP address to all people connected to the network and this can be source of vulnerability for the ISP. In this case you can only connect to the IRC via SSH tunnel. 

For this setup you need to have Virtual Private Server so that you can tunnel the your connection to the VPS and bypass the it with ip address of your VPS. One of the requirements for this is your VPS server should be running SSH daemon and your local machine should have SSH client to create SSH tunnel. 

#### Creating ssh tunnel

``` ssh -L localhost:6667:<irc-host>:6667 <user>@<ssh-host> -N -v``` 

for eg: For connecting the OFTC network through SSH tunnel. 

``` ssh -L localhost:6667:irc.oftc.net:6667 <user>@<ssh-host> -N -v```

#### Connecting to the server

Now we successfully created the SSH tunnel and ready for the connection. Open the weechat and connect to the respective newtork. 

- Adding oftc server 

``` /server add oftc localhost ``` 

Here localhost is connected to the VPS ip address where SSH tunnel is set up. 

- Connecting to the server

``` /connect localhost ``` 

Voila! Now you are connected to the IRC server. 

Hope instructions are pretty clear and able to follow through. 
Thankyou ! 
 
