# How to use reverse proxy server using Caddy, VPC (private virtual cloud) and nodejs fastify

My Load Balancer IP address: http://24.199.69.238

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
* Caddy to host server proxy
* Volta to install node
* Fastify for NodeJs server
* Text editors: Vim or Nano

## Prepared Steps

4. Install Volta, Node and Fastify in server
  **Important** We MUST install Volta before installing Node and Fastify
  
  > To download volta, run command: curl https://get.volta.sh | bash
  > To source bash file, run command: source ~/.bashrc
  
  After that, we can use volta to install node and npm
  
  > To install node, run command: volta install node
  > To install npm, run command: volta install npm


## Instructions

### Step 1: create droplets, firewall and VPC

1. Generate SSH keys: refer to [the video](https://vimeo.com/758870226/f75da348fc?embedded=true&source=vimeo_logo&owner=17609105)
2. Set up VPC and Load Balancer in Digital Ocean
  In **Networking** section, choose **VPC**, and then click **Create VPC**
  The desired output should be
  ![load balancer picture](/images/load-balancer-5.png)
  **Note**: 
  > The tag of load balancer MUST match the <ins>tag</ins> of the droplets
  > When creating load balancer and droplets, make sure to have same VPC 
  ![Tag of load balancer picture](/images/load-balancer-4.png)
  
  !(VPC load balancer picture)(/images/load-balancer-3.png)
  
  
3. Set up Firewall
  * Step 1: In **Networking** section, choose **Firewall**, and then click **Create Firewall**
  ![create firewall picture](/images/firewall-create.png)
  
  * Step 2: In **Inbound Rules**, make sure the <ins>HTTPS</ins> type has sources from load balancer
  ![Inbound Rules picture](/images/firewall-create-1.png)
  
  **Note**
  > Make sure that firewall has same <ins>tag</ins> with Droplets
  ![tag in firewall](/images/firewall-create-2.png)
  
  After creating, it should show like the below image
  ![firewall after created](/images/firewall-created.png)
  
<p>***For more information about how to set up VPC & Firewall, refer to [the video](https://vimeo.com/775412708/4a219b37e7)***</p>


### Step 2: create regular user
Connect to the droplets using the SSH key generated
> Command to connect droplets from local host: ssh root@<IP-address>
> To add new user using bash shell, run command: useradd -ms /bin/bash <username>
> To add sudo privilegies to regular user, run command: usermod -aG sudo <username>
> To change password, run command: passwd <username>
  
### Step 3: Install Web server using Caddy
  > To download Caddy, run command: wget https://github.com/caddyserver/caddy/releases/download/v2.6.2/caddy_2.6.2_linux_amd64.tar.gz
  > To unarchive tar.gz file, run command: tar xvf caddy_2.6.2_linux_amd64.tar.gz

  ![image to download Caddy](/images/caddy-download.png)
  
  ![image to unarchive Caddy](/images/caddy-extract.png)
  
  > Move caddy file to usr/bin, run command: sudo cp caddy /usr/bin/
  > To change user ownership, run command: sudo chown root:caddy
  
### Step 4
  1. Write web app
  2. In local host, create directory and make node project
  
                                         
