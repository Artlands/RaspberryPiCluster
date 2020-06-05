# Build a Raspberry Pi cluster
In this repo, we summarize the experience of building a Raspberry Pi cluster. 
The hardware includes:
- Four [Raspberry Pi 4 B boards](https://smile.amazon.com/gp/product/B07TC2BK1X/ref=ppx_yo_dt_b_asin_title_o03_s01?ie=UTF8&psc=1)
- Four 64GB MicroSD cards, one for each board
- Cables: four ethernet cables, four MicroUSB cables, one Micro HDMI cable
- One [4-port USB Hub](https://www.amazon.com/Transcend-Information-SuperSpeed-USB-TS-HUB3K/dp/B005D69QD8/ref=sr_1_2?dchild=1&keywords=transend+4-hub&qid=1591331613&s=electronics&sr=1-2)
- One 5-port switch
- One [cluster rack](https://smile.amazon.com/gp/product/B07CTG5N3V/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1) that has coolers installed
## Cluster assemble
Easy and self-explanatory. Lots of related videos on Youtube. 

We're going to access each node using wireless LAN and use Ethernet port for communication among nodes. Thus the switch does not have internet connection.
## OS installation
We want to use CentOS in our cluster. To be noticed, the distribution for armv7hl platform is called "CentOS Userland Linux" and not "CentOS Linux". Find the appropriate image for Raspberry Pi: http://isoredirect.centos.org/altarch/7/isos/armhfp. We do not need GUI, thus we select [armv7hl-RaspberryPI-Minimal](http://mirror.dal.nexril.net/centos-altarch/7.8.2003/isos/armhfp/CentOS-Userland-7-armv7hl-RaspberryPI-Minimal-4-2003-sda.raw.xz). Download the zip file and unzip it to iso image. Image all microSD cards with CentOS7 using [Raspberry Pi Imager](https://www.raspberrypi.org/blog/raspberry-pi-imager-imaging-utility/). The default root passward is **centos**.
## Expand capacity
There is a ``/root/README`` file that describes how to expand the root partition to capacity of the MicroSD. Follow the instructions to expand the root filesystem using: ``rootfs-expand``

```
== CentOS 7 userland ==

If you want to automatically resize your / partition, just type the following (as root user):
rootfs-expand
```