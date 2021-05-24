+++
author = "Arran Short"
date = 2011-02-17T11:01:00Z
description = ""
draft = false
slug = "ecu-interface-using-openwrt-on-zoom"
title = "ECU interface using Openwrt on Zoom 4501. Part 1"

+++


I’ve been seeing the increase of  Iphone integration with cars recently, most notably the generic OBD2 wifi/bluetooth interfaces and the accompanying apps.

This got me thinking, can it be done for pre obd2 or standalone ecus. I had a look at target devices that would suit and the only cross-platform connection they had that was reliable is wifi.

Now most ecus use a USB connection so I set out to find hardware with wifi and a USB host port, and came across affordable 3g wifi routers. A quick scan on eBay an a bid was made on a [Zoom 4501](http://www.zoom.com/graphics/datasheets/mobile_broadband/4501_28410_spec.pdf).

The Zoom 4501 has 4MB flash, 32MB ram and a rt3050 ralink chipset which seems to have reasonable linux support. [High Res Scan](http://i6.photobucket.com/albums/y221/sord_fish/scan.jpg)

The router arrived today so my first mission is get openwrt running.

Soldered a header in j2 and connected a max232   
opened hyperterm @ 57600 8-n-1 output is below 

    JRecovery Version R1.1 2009/12/23 15:10 
    Flash MXIC-22A7 0xBF000000-0x400000 x16
    ……………  
    Starting kernel @80000000…  
      
      
    LINUX started…  
      
      
     THIS IS ASIC  
    Linux version 2.6.21 (charles@uranus) (gcc version 3.4.2) #4 Mon Oct 18 10:59:51  
     CST 2010  
      
      
    The CPU feqenuce set to 320 MHz  
    CPU revision is: 0001964c  
    Determined physical RAM map:  
     memory: 02000000 @ 00000000 (usable)  
    Built 1 zonelists.  Total pages: 8128  
    Kernel command line: console=ttyS1,57600n8 root=/dev/mtdblock3  
    Primary instruction cache 32kB, physically tagged, 4-way, linesize 32 bytes.  
    Primary data cache 16kB, 4-way, linesize 32 bytes.  
    Synthesized TLB refill handler (20 instructions).  
    Synthesized TLB load handler fastpath (32 instructions).  
    Synthesized TLB store handler fastpath (32 instructions).  
    Synthesized TLB modify handler fastpath (31 instructions).  
    Cache parity protection disabled  
    cause = 80800058, status = 1100ff00  
    PID hash table entries: 128 (order: 7, 512 bytes)  
    calculating r4koff… 00138800(1280000)  
    CPU frequency 320.00 MHz  
    Using 160.000 MHz high precision timer.  
    Console: colour dummy device 80×25  
    Dentry cache hash table entries: 4096 (order: 2, 16384 bytes)  
    Inode-cache hash table entries: 2048 (order: 1, 8192 bytes)  
    Memory: 29304k/32768k available (2382k kernel code, 3464k reserved, 557k data, 1  
    24k init, 0k highmem)  
    Mount-cache hash table entries: 512  
    NET: Registered protocol family 16  
    SCSI subsystem initialized  
    usbcore: registered new interface driver usbfs  
    usbcore: registered new interface driver hub  
    usbcore: registered new device driver usb  
    Time: MIPS clocksource has been installed.  
    NET: Registered protocol family 2  
    IP route cache hash table entries: 1024 (order: 0, 4096 bytes)  
    TCP established hash table entries: 1024 (order: 1, 8192 bytes)  
    TCP bind hash table entries: 1024 (order: 0, 4096 bytes)  
    TCP: Hash tables configured (established 1024 bind 1024)  
    TCP reno registered  
    squashfs: version 3.2-r2 (2007/01/15) Phillip Lougher  
    squashfs: LZMA suppport for slax.org by jro  
    fuse init (API version 7.8)  
    io scheduler noop registered (default)  
    FLASH_API: MAN_ID=C2 DEV_ID=22A7 SIZE=4MB  
      
      
    ——————GPIO————————–  
     GPIOMODE:2df  
    SLIC INTR ==> gpio 0  
    Ralink gpio driver initialized  
    HDLC line discipline: version $Revision: 1.1.1.1 $, maxframe=4096  
    N_HDLC line discipline registered.  
    Serial: 8250/16550 driver $Revision: 1.3 $ 2 ports, IRQ sharing disabled  
    serial8250: ttyS0 at I/O 0xb0000500 (irq = 37) is a 16550A  
    serial8250: ttyS1 at I/O 0xb0000c00 (irq = 12) is a 16550A  
    loop: loaded (max 8 devices)  
    rdm_major = 254  
    GDMA1_MAC_ADRH — : 0x00000000  
    GDMA1_MAC_ADRL — : 0x00000000  
    Ralink APSoC Ethernet Driver Initilization. v1.60  256 rx/tx descriptors allocat  
    ed, mtu = 1500!  
    GDMA1_MAC_ADRH — : 0x00005051  
    GDMA1_MAC_ADRL — : 0x040f5b2c  
    PROC INIT OK!  
    TX100 AD/DA current bias: 7054  
    TX100 slew rate control: 0050  
    PPP generic driver version 2.4.2  
    PPP Deflate Compression module registered  
    PPP BSD Compression module registered  
    NET: Registered protocol family 24  
    ralink flash device: 0x400000 at 0xbf000000  
    Ralink SoC physically mapped flash: Found 1 x16 devices at 0x0 in 16-bit bank  
     Amd/Fujitsu Extended Query Table at 0x0040  
    Ralink SoC physically mapped flash: Swapping erase regions for broken CFI table.  
      
      
    number of CFI chips: 1  
    cfi_cmdset_0002: Disabling erase-suspend-program due to code brokenness.  
    Creating 6 MTD partitions on “Ralink SoC physically mapped flash”:  
    0x00000000-0x00400000 : “Whole”  
    0x00000000-0x00010000 : “Bootloader”  
    0x00010000-0x00110000 : “Kernel”  
    0x00110000-0x003a0000 : “RootFS”  
    0x003a0010-0x003f0000 : “UI”  
    mtd: partition “UI” doesn’t start on an erase block boundary — force read-only  
    0x003f0000-0x00400000 : “Config”  
    block2mtd: version $Revision: 1.1.1.1 $  
    usbcore: registered new interface driver usbhid  
    drivers/usb/input/hid-core.c: v2.6:USB HID core driver  
    u32 classifier  
    Netfilter messages via NETLINK v0.30.  
    nf_conntrack version 0.5.0 (256 buckets, 2048 max)  
    Register conntrack protocol helper for ESP…  
    GRE over IPv4 tunneling driver  
    Init IP_nat_proto_esp register.  
    ip_tables: (C) 2000-2006 Netfilter Core Team, Type=Restricted Cone  
    arp_tables: (C) 2002 David S. Miller  
    TCP cubic registered  
    NET: Registered protocol family 1  
    NET: Registered protocol family 17  
    802.1Q VLAN Support v1.8 Ben Greear <greearb></greearb>@candelatech.com>  
    All bugs added by David S. Miller <davem></davem>@redhat.com>  
    VFS: Mounted root (squashfs filesystem) readonly.  
    Freeing unused kernel memory: 124k freed  
    Algorithmics/MIPS FPU Emulator v1.5  
    Ralink HotFix  
    switch register base addr to 0xb0180000  
    write offset 0x500, value 0x31a65  
    write offset 0x500, value 0x31b23  
    Inter-|   Receive  
    phy_tx_ring = 0x01c76000, tx_ring = 0xa1c76000, size: 16 bytes  
      
      
    phy_rx_ring = 0x01c77000, rx_ring = 0xa1c77000, size: 16 bytes  
     |  Transmit  
     fRT305x_ESW: Link Status Changed  
    ace |bytes    paGDMA1_FWD_CFG = 710000  
    ckets errs drop fifo frame compressed multicast|bytes    packets errs drop fifo  
    colls carrier compressed  
      eth2:       0       0    0    0    0     0          0         0        0  
     0    0    0    0     0       0          0  
        lo:       0       0    0    0    0     0          0         0        0  
     0    0    0    0     0       0          0  
      gre0:       0       0    0    0    0     0          0         0        0  
     0    0    0    0     0       0          0  
    dwc_otg: version 2.72a 24-JUN-2008  
    DWC_otg: Core Release: 2.66a  
    DWC_otg: Periodic Transfer Interrupt Enhancement – disabled  
    DWC_otg: Multiprocessor Interrupt Enhancement – disabled  
    DWC_otg: Using DMA mode  
    DWC_otg: Device using Buffer DMA mode  
    dwc_otg lm0: DWC OTG Controller  
    dwc_otg lm0: new USB bus registered, assigned bus number 1  
    dwc_otg lm0: irq 18, io mem 0x00000000  
    DWC_otg: Init: Port Power? op_state=1  
    DWC_otg: Init: Power Port (0)  
    usb usb1: configuration #1 chosen from 1 choice  
    hub 1-0:1.0: USB hub found  
    hub 1-0:1.0: 1 port detected  
    Load RT2880 Timer Module(Wdg/Soft)  
    ipt_webstr: module license ‘unspecified’ taints kernel.  
     flash_open: flash_fd=3  
    Mount D Section.  
    mount: /dev/mtdblock4 is write-protected, mounting read-only  
    timezone:0  
    dsttime:0  
     flash_open: flash_fd=9  
    Thu Jan  1 00:00:00 UTC 2009  
    timezone:0  
    dsttime:0  
    switch reg write offset=14, value=405555  
    switch reg write offset=50, value=2001  
    switch reg write offset=98, value=7f3f  
    switch reg write offset=e4, value=3f  
    switch reg write offset=40, value=1002  
    switch reg write offset=44, value=1001  
    switch reg write offset=48, value=1001  
    switch reg write offset=70, value=ffff417e  
    Set: phy[0].reg[0] = 3300  
    eth2.1: Setting MAC address to  00 40 36 3d 07 ec.  
    device eth2 entered promiscuous mode  
    VLAN (eth2.1):  Setting underlying device (eth2) to promiscious mode.  
    ifconfig eth2.1 hw ether 0040363D07EC  
    eth2.1: dev_set_promiscuity(master, 1)  
    device eth2.1 entered promiscuous mode  
    killall: ated: no process killed  
    sh: lld2d: not found  
    eth2.2: Setting MAC address to  00 40 36 3d 07 eb.  
    br0: port 1(eth2.1) entering learning state  
    br0: topology change detected, propagating  
    br0: port 1(eth2.1) entering forwarding state  
    Length of MAC:6  
     mac:0:40:36:3d:7:ed:  
    —-  
      
      
      
      
    === pAd = c0448000, size = 408704 ===  
      
      
    <– RTMPAllocAdapterBlock, Status=0  
    RX DESC a1f2e000  size = 2048  
    <– RTMPAllocTxRxRingMemory, Status=0  
    Key1Str is Invalid key length(0) or Type(0)  
    Key2Str is Invalid key length(0) or Type(0)  
    Key3Str is Invalid key length(0) or Type(0)  
    Key4Str is Invalid key length(0) or Type(0)  
    1. Phy Mode = 9  
    2. Phy Mode = 9  
    3. Phy Mode = 9  
    MCS Set = ff 00 00 00 01  
    Main bssid = 00:40:36:3d:07:ed  
    <==== rt28xx_init, Status=0  
    0x1300 = 00064380  
    device ra0 entered promiscuous mode  
    br0: port 2(ra0) entering learning state  
    br0: topology change detected, propagating  
    br0: port 2(ra0) entering forwarding state  
    ==== NAT START ====  
    timezone:0  
    dsttime:0  
    fwd_adjust_mss setup  
    /var/nat-draft.uyg start ok  
    udhcpd (v0.9.9-pre) started  
    Unable to open /var/run/udhcpd.leases for reading  
    timezone:0  
    dsttime:0  
    ============= AMIT UPNP Start =============  
    WAN_IF=eth2.2,LAN_IF=br0  
    eth2.2 br0  
    iptables: Chain already exists  
    iptables: Chain already exists  
    AGP Server Linux Version 1 (c) 2008/10/3  
    192.168.1.1  
    192.168.1.1  
    192.168.1.1  
    flash_open: flash_fd=9

