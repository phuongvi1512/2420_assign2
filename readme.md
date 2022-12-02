# How to use reverse proxy server using Caddy, VPC (private virtual cloud) and nodejs fastify

## Description
The assignment is to
* Create VPC 
* Create load balancer in Digital Ocean
* Create reverse proxy server in Caddy
* Install Nodejs and NPM on server

## Prerequisites
* WSL and Digital Ocean droplets (ubuntu-01 and ubuntu-02)
* SSH key to connect to the droplets
* Ubuntu 22.10
* Windows Terminal 
* Volta to install node
* Fastify for NodeJs server
* Text editors: Vim or Nano

## Prepared Steps
1. Generate SSH keys: refer to [the video](https://vimeo.com/758870226/f75da348fc?embedded=true&source=vimeo_logo&owner=17609105)
2. Set up VPC and Load Balancer in Digital Ocean
  The desired output should be
  ![load balancer picture](/images/load-balancer-5.png)
  > **Note**: the tag of load balancer MUST match the tag of the droplets
  ![Tag of load balancer picture](/images/load-balancer-4.png)
3. Set up Firewall
***For more information about how to set up VPC & Firewall, refer to [the video](https://vimeo.com/775412708/4a219b37e7)***
                                         
