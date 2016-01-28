This is a Makefile to let OpenWrt users compile and install jq on their devices

You can find more info of jq here `https://stedolan.github.io/jq/`.

To compile, you need to :

    ln -s /path_to_jq /path_to_openwrt_buildroot_topdir/package/utils/
    cd /path_to_openwrt_buildroot_topdir
    make menuconfig, find jq under Utilities submenu
    make package/utils/jq/{clean,compile} V=s

Then you should find jq ipk in `path_to_openwrt_buildroot_topdir/bin` directory

Since jq has not been added to OpenWrt package list, if you failed to download its source code, please download it from here `https://github.com/stedolan/jq/releases/download/jq-1.5/jq-1.5.tar.gz` and copy it to your `path_to_openwrt_buildroot_topdir/dl` directory then it should work.