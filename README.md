The usb zigbee module on the cc2531 chip did not work for me. There was no driver in the linux cdc-acm kernel. 
In order not to rebuild the kernel, I used this patch.


Who doesn't have linux kernel current installed:

    sudo dpkg -i /opt/linux-headers-current-ky_1.x.x_riscv64.deb

    git clone https://github.com/Tolcen/ttyACM-driver-for-OrangepiRV2.git

    cd ttyACM-driver-for-OrangepiRV2

    make

The cdc-acm.ko file will appear in the folder. 

    modprobe /....../....../ttyACM-driver-for-OrangepiRV2/cdc-acm.ko

    
