---
title: "Snort 3.0 + Snowl(GUI)"
date: 2021-04-25T00:22:03+01:00
draft: false
---

**Snort 3.0 + Snowl(GUI) installation on Debian 10**

# Steps




cd libpcap-1.10.0 157 ./configure --prefix=/usr && make 158 make install 159 cd .. 160 ./configure && make && sudo make install
161 tar xvzf snort-2.9.17.1.tar.gz 162 163 cd snort-2.9.17.1 164 ./configure --enable-sourcefire && make && sudo make 165 wget https://www.snort.org/downloads/community/community-rules.tar.gz -O community-rules.tar.gz
166 tar -xvzf community-rules.tar.gz

wget https://snowl.io/download/snowl-install-debian.sh && bash ./snowl-install-debian.sh



sudo su

cd tmp

wget https://www.snort.org/downloads/snort/daq-2.0.7.tar.gz
                      
wget https://www.snort.org/downloads/snort/snort-2.9.17.1.tar.gz

tar xvzf daq-2.0.7.tar.gz
                      
cd daq-2.0.7
./configure && make && sudo make install

tar xvzf snort-2.9.17.1.tar.gz
                      
cd snort-2.9.17.1
./configure --enable-sourcefire && make && sudo make install

** If you have issues compiling, please follow these steps **

apt install tcpdump

cd /tmp

wget https://www.tcpdump.org/release/libpcap-1.10.0.tar.gz

cd libpcap-1.10.0 

./configure --prefix=/usr && make

 make install

-----------------------

wget https://www.snort.org/downloads/community/community-rules.tar.gz -O community-rules.tar.gz

tar -xvzf community-rules.tar.gz -C /etc/snort/rules


--------------

**set interface/(s) in promiscuous mode **

vim /etc/systemd/system/snort3-nic.service

[Unit]
Description=Set Snort 3 NIC in promiscuous mode and Disable GRO, LRO on boot
After=network.target

[Service]
Type=oneshot
ExecStart=/bin/ip link set dev eth0 promisc on
ExecStart=/sbin/ethtool -K eth0 gro off lro off
ExecStart=/bin/ip link set dev eth1 promisc on
ExecStart=/sbin/ethtool -K eth1 gro off lro off
TimeoutStartSec=0
RemainAfterExit=yes

[Install]
WantedBy=default.target
-----------------------

Reload systemd configuration settings;

systemctl daemon-reload

Start and enable the service on boot;

systemctl enable --now snort3-nic.service

**install snowl**

cd /tmp


wget https://snowl.io/download/snowl-install-debian.sh && bash ./snowl-install-debian.sh

apt install apache2

or

apt install nginx

apt install sudo

wget https://snowl.io/download/snowl_1.7.1_amd64.deb && dpkg -i ./snowl_1.7.1_amd64.deb

/opt/snowl/snowl-configure-httpd
-----------------
 http://[IP address]:5500


admin:123456



