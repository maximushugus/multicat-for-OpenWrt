In this repository you will find in the sources folder, the sources of Multicat for Videolan modified te be able to compile for OpenWt routers.

In the bin folder there are the compiled binaries of Multicat for the MIPSEL architecture.

To cross compile this program for you architecture for OpenWrt :
1) Get the sdk for your architecture : https://openwrt.org/docs/guide-developer/using_the_sdk
2) Execute these commands, replacing the necessary parts (you can find them by exploring the sdk folder)

export STAGING_DIR=place-here-the-directory-of-the-sdk/staging_dir/

export TOOLCHAIN_DIR=$STAGING_DIR/toolchain-architecture-_gcc-place-here-the-version-of-gcc-you-find-in-the-directory_musl/

export LDCFLAGS=$TOOLCHAIN_DIR/usr/lib

export LD_LIBRARY_PATH=$TOOLCHAIN_DIR/usr/lib

export PATH=$TOOLCHAIN_DIR/bin:$PATH

export CC=$TOOLCHAIN_DIR/bin/mipsel-openwrt-linux-gcc

export LD=$TOOLCHAIN_DIR/bin/mipsel-openwrt-linux-ld
3) Go in the directory of the sources of this repository
4) Cross-compile the libev with this command :

make
5) The "multicat" file created is the binary for your architecture
