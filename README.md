https://github.com/Mr-Bossman/licheepi-nano-buildroot.git

cd licheepi-nano-buildroot

git submodule update --init

cd buildroot

make BR2_EXTERNAL=$PWD/../ licheepi_nano_defconfig

make -j4

sudo dd status=progress oflag=sync bs=4k if=output/images/sdcard.img of=/dev/sdX; sync