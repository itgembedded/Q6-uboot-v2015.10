# Q6_uboot_v2015_10
mx6q/dl/s/spl Q6 u-boot v2015.10 
 
# Download repository
    git clone https://github.com/itgembedded/Q6-uboot-v2015.10.git
    cd Q6-uboot-v2015.10
 
# Install cross compiler
    apt-get install gcc-arm-linux-gnueabihf
 
# Setup cross compiler
    export CROSS_COMPILE=arm-linux-gnueabihf-
    export ARCH=arm
 
# Build (imx6q)
    make distclean
    make Q6_config
    make
    cp u-boot.imx /tftp/uboot-Q6.imx
 
# To attempt to Update UBOOT in SPI try from U-Boot:
# 	run update_spi_uboot 
# 	mw.b 0x10800000 0xFF 0x80000;tftp 0x10800000 imx6/u-boot-imx6q-openrex.imx;sf probe;sf erase 0x0 0x80000;sf write 0x10800000 0x400 0x80000


# Changes focused on:
#	include/configs/Q6.h
#	include/configs/Q6_common.h
#	board/jci/Q6/Q6.c
