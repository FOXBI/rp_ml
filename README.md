# Repill Multiloader

# Requirement
1, Redpill-Multiloader_7.1-42661.img file Download<br>
   Please understand that Google Drive is used because of its large capacity. There is a link below.

2. It is the same as using the existing Redpill Tinycore or a separately made loader.

3. ESXi Enviroment<br>
   (Bootloader SATA1 (1:0), DataDisk SATA0 (0:0))
   
   or
   
   Baremetal Enviroment<br>
   (It can be used by making a USB with rufus, etc.)

# How to RUN Redpill Multiloader

[![tr_st](http://img.youtube.com/vi/NxuISAZaRRk/0.jpg)](https://youtu.be/NxuISAZaRRk) 

1.  Redpill-Multiloader_7.1-42661.zip decompression

2. Modify /boot/grub/grub.cfg by mounting the first partition on OSFmount or TC<br>
   set sn=1234SQRDD5678<br>
   set netif_num=1<br>
   set mac1=001122334455<br>
   set SataPortMap=9<br>
   set DiskIdxMap=0<br>
   set SasIdxMap=0

  The USB or Boot oder part is an additional setting and does not necessarily need to be modified.
 

3. Convert Redpill-Multiloader_7.1-42661.img  to Redpill-Multiloader_7.1-42661.vmdk, Redpill-Multiloader_7.1-42661-flat.vmdk

4. Register as boot disk in ESXi VM (default SATA1 (1:0))

5. Enter GRUB and use the desired DSM version

# Additional notes

1. It is built by default for EXSi and can be modified after additional builds if necessary.<br>
    (I'll update the method further.)

2. Due to variable processing for sn, mac, etc., it is temporarily modified in GRUB state and cannot be used.

3. The video has been processed only with the popular DS918+, DS920+, DS1621+, DS3622xs+, and DVA3221,<br>
    and DS3615xs and DS3617xs are also available.

4. USB is handled as a submenu, and pressing ESC will return to the upper menu.

5. In the future, we plan to make Multiloader production possible directly on TC through tr_cb.sh.<br>
   https://github.com/FOXBI/tr_cb
   
6. Serial console enable
[![tr_st](http://img.youtube.com/vi/6zvQ_Ss8ZIw/0.jpg)](https://youtu.be/6zvQ_Ss8ZIw) 


# Attachement

Download : (Google drive link - 400MB) -  Please understand that Google Drive is used because of its large capacity

<b>https://drive.google.com/file/d/1t1cOPMmlSg3c65mXJBeI_44yor_sp9Xl/view?usp=sharing</b>

