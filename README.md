# maclookup
Public Domain software created by Stuart Henderso on December 2011

# USAGE

You can echo one or a list (one per line) of MAC Addresses as follows:

```
$ echo "00:09:0f:ca:f3:c0" | maclookup 
00:09:0f:ca:f3:c0 (Fortinet Inc.)
```
or

```
cat list-of-macs.txt | maclookup
```

You can also get Vendors from your ARP Table output like this:

```
arp -an | maclookup
? (192.168.19.77) at 00:1f:29:ca:fe:ca (Hewlett Packard) [ether] on eth0
? (192.168.19.75) at 00:00:87:ca:fe:cb (HITACHI, LTD.) [ether] on eth0
? (192.168.19.74) at 00:26:cb:ca:fe:cc (CISCO SYSTEMS, INC.) [ether] on eth0
? (192.168.19.73) at 00:50:56:ca:fe:cd (VMware, Inc.) [ether] on eth0
? (192.168.19.73) at 00:1a:64:ca:fe:cf (IBM Corp) [ether] on eth0

```

# Supported Formats

At the moment the following formats are supported:

```
00:11:22:33:44:55 - Traditional
001122-334455 - (HP Procurve)
0011-2233-4455 - (HP H3C)
0011.2233.4455 - (Cisco)
```

# OSX
```
NOT READY YET !
```
You can install arp-scan using:

```
brew install arp-scan
```
Please take into account that you will need to modify the path to be able to read the needed files, usually
they are located at (this is an example in case the arp-scan version is 1.9, modify it as needed):
```
$ ls /usr/local/Cellar/arp-scan/1.9/share/arp-scan/
ieee-iab.txt   ieee-oui.txt   mac-vendor.txt
```

# Linux

Just instal arp-scan, then clone this repo and place the maclookup file into your favourite exec path, an example
using Debian/Ubuntu would be:

```
$ sudo apt-get install -y arp-scan
```

Using CentOS 7 (epel repo):

```
$ sudo yum install -y arp-scan 
```

Clone repo files:

```
$ git clone https://github.com/h0cin/maclookup.git "maclookup" && cd maclookup && chmod 755 maclookup
```

Then move the file to your favourite binary location:

```
$ sudo mv maclookup /usr/local/bin 
```

Check availability:

```
$ which maclookup
```


# OpenBSD 

OpenBSD is awesome and only needs you to install the package:

```
$ doas pkg_add -vim maclookup
```
