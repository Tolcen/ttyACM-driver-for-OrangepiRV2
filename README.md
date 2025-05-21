The usb zigbee module on the cc2531 chip did not work for me. There was no driver in the linux cdc-acm kernel. 
In order not to rebuild the kernel, I used this patch.
---
It was tested only on Ubuntu noble kernel 6.6.63-ky orangepirv2(riscv64)
---

Who doesn't have linux kernel current installed:

    sudo dpkg -i /opt/linux-headers-current-ky_1.x.x_riscv64.deb

------

    git clone https://github.com/Tolcen/ttyACM-driver-for-OrangepiRV2.git

    cd ttyACM-driver-for-OrangepiRV2

    make

The cdc-acm.ko file will appear in the folder. 

    modprobe /....../....../ttyACM-driver-for-OrangepiRV2/cdc-acm.ko
----
For homeassistant to access ttyACM0, I had to register in rc.local:

      chmod 777 /dev/ttyACM0

    
