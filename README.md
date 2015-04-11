# imx6_rex_uboot_kk442
imx6q/dl rex u-boot for android kitkat

# Download repository
git clone https://github.com/voipac/imx6_rex_uboot_kk442<br />
cd imx6_rex_uboot_kk442<br />

# Setup cross compiler
export PATH="/opt/gcc-linaro-arm-linux-gnueabihf-4.8-2014.04_linux/bin:~/workdir/bin:$PATH"<br />
export CROSS_COMPILE=arm-linux-gnueabihf-<br />
export ARCH=arm<br />

# Build (imx6dl)
make clean<br />
make mx6dl_rex_config<br />
make -j4<br />
cp -av u-boot.bin /srv/tftp/imx6/u-boot-0x27800000_imx6dl_$(date "+%Y%m%d").bin<br />

# Build (imx6q)
make clean<br />
make mx6q_rex_config<br />
make -j4<br />
cp -av u-boot.bin /srv/tftp/imx6/u-boot-0x27800000_imx6q_$(date "+%Y%m%d").bin<br />
