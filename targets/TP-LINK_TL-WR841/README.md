

http://router-mod.blogspot.com/2018/09/why-needed-to-investigate-your-routers.html


tftp recovery:
tftp recovery works on v14. press and hold reset button after power on. Device IP is 192.168.0.2, Server IP is 192.168.0.66, Filename: tp_recovery.bin

Serial console
I used the internal serial port for modification. It's 115.200 8N1 3,3V TTL, so use a ftdi adapter. Strangely I need a pullup resistor on RX (router side). Otherwise it does not get my inputs.
Pressing 't' after reset enters bootloader.
Original recovery commands are: ""tftp 0x80060000 tp_recovery.bin;erase tplink 0x10000 0x3d0000;cp.b 0x80070000 0x10000 0x3d0000"



https://www.zerodayinitiative.com/blog/2019/9/2/mindshare-hardware-reversing-with-the-tp-link-tl-wr841n-router


https://openwrt.org/toh/tp-link/tl-wr841nd



https://wiki.dd-wrt.com/wiki/index.php/TP-Link_TL-WR841nd_v9

https://wiki.dd-wrt.com/wiki/index.php/TP-LINK_TL-WR841ND

