# tigervnc源码编译(Linux)

## 编译环境

**X86环境：（VMware虚拟机）**

银河麒麟V10SP1：5.4.18-35-generic

**arm环境：**

银河麒麟V10-gfb：5.4.18-52-generic

银河麒麟V10-gfb：5.4.18-65-generic

Ubuntu 20.04.5 LTS：5.10.110

## 下载tigervnc源码

github仓库地址：https://github.com/TigerVNC/tigervnc

1.13.1-release版本：https://github.com/TigerVNC/tigervnc/releases/tag/v1.13.1

## 安装依赖及编译

所需依赖如下

```bash
sudo apt-get install libpixman-1-dev
sudo apt-get install libfltk1.3-dev
sudo apt-get install libgnutls28-dev
sudo apt-get install libgmp3-dev
sudo apt-get install nettle-dev
sudo apt-get install libhogweed5
sudo apt-get install libxtst-dev
sudo apt-get install appstream
sudo apt-get install gettext
sudo apt-get install libjpeg-dev
sudo apt-get install libpam0g-dev
sudo apt-get install libselinux1-dev
sudo apt-get install libxdamage-dev
sudo apt-get install libxfixes-dev
sudo apt-get install libxrandr-dev
sudo apt-get install libxi-dev

# 汇总
sudo apt-get install libpixman-1-dev libfltk1.3-dev libgnutls28-dev libgmp3-dev nettle-dev libhogweed5 libxtst-dev appstream gettext libjpeg-dev libpam0g-dev libselinux1-dev libxdamage-dev libxfixes-dev libxrandr-dev libxi-dev
```



编译过程

```bash
# 解压源码
tar -xvf tigervnc-1.13.1.tar.gz

# 进入目录，新建一个build目录
cd tigervnc-1.13.1/
mkdir build
cd build/

# cmake生成Makefile文件
cmake ..

-- The C compiler identification is GNU 9.3.0
-- The CXX compiler identification is GNU 9.3.0
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- CMAKE_BUILD_TYPE = Release
-- VERSION = 1.13.1
-- BUILD_TIMESTAMP = 2023-03-28 06:59
-- Found X11: /usr/include   
-- Looking for XOpenDisplay in /usr/lib/x86_64-linux-gnu/libX11.so;/usr/lib/x86_64-linux-gnu/libXext.so
-- Looking for XOpenDisplay in /usr/lib/x86_64-linux-gnu/libX11.so;/usr/lib/x86_64-linux-gnu/libXext.so - found
-- Looking for gethostbyname
-- Looking for gethostbyname - found
-- Looking for connect
-- Looking for connect - found
-- Looking for remove
-- Looking for remove - found
-- Looking for shmat
-- Looking for shmat - found
-- Found ZLIB: /usr/lib/x86_64-linux-gnu/libz.so (found version "1.2.11") 
-- Found PkgConfig: /usr/bin/pkg-config (found version "0.29.1") 
-- Checking for module 'pixman-1'
--   Found pixman-1, version 0.38.4
-- Found Gettext: /usr/bin/msgmerge (found version "0.19.8.1") 
-- Performing Test ICONV_HAVE_WERROR
-- Performing Test ICONV_HAVE_WERROR - Success
-- Performing Test ICONV_SECOND_ARGUMENT_IS_CONST
-- Performing Test ICONV_SECOND_ARGUMENT_IS_CONST - Failed
-- Found Iconv: /usr/lib/x86_64-linux-gnu/libc.so
-- Looking for dgettext
-- Looking for dgettext - found
-- Checking for module 'libavcodec'
--   Found libavcodec, version 58.54.100
-- Checking for module 'libavutil'
--   Found libavutil, version 56.31.100
-- Checking for module 'libswscale'
--   Found libswscale, version 5.5.100
-- Found JPEG: /usr/lib/x86_64-linux-gnu/libjpeg.so (found version "80") 
-- Performing Test FOUND_LIBJPEG_TURBO
-- Performing Test FOUND_LIBJPEG_TURBO - Success
-- Found FLTK: fltk_images;fltk  
-- Found GnuTLS: /usr/lib/x86_64-linux-gnu/libgnutls.so (found version "3.6.13") 
-- Checking for module 'gmp'
--   Found gmp, version 6.2.0
-- Checking for module 'nettle>=3.0'
--   Found nettle, version 3.5.1
-- Checking for module 'hogweed'
--   Found hogweed, version 3.5.1
-- Looking for include file security/pam_appl.h
-- Looking for include file security/pam_appl.h - found
-- Looking for pam_start
-- Looking for pam_start - found
-- Looking for include file selinux/selinux.h
-- Looking for include file selinux/selinux.h - found
-- Creating static libtool control file for target os
-- Creating static libtool control file for target rdr
-- Creating static libtool control file for target network
-- Creating static libtool control file for target rfb
-- Creating static libtool control file for target unixcommon
-- Configuring done
-- Generating done
-- Build files have been written to: /home/xxxx/xxxx/tigervnc-1.13.1/build


# 编译、安装
make -j8
sudo make install
```

## 报错及解决方法

### cmake

#### No package 'pixman-1' found

安装对应的包

```bash
sudo apt-get install libpixman-1-dev
```

#### Could NOT find FLTK (missing: FLTK_LIBRARIES FLTK_INCLUDE_DIR)

安装对应的包

```bash
sudo apt-get install libfltk1.3-dev
```

#### Could NOT find Gettext (missing: GETTEXT_MSGMERGE_EXECUTABLE GETTEXT_MSGFMT_EXECUTABLE) 

安装对应的包

```bash
sudo apt-get install gettext
```

#### Could NOT find JPEG (missing: JPEG_LIBRARY JPEG_INCLUDE_DIR)

安装对应的包

```bash
sudo apt-get install libjpeg-dev
```

#### Could not find PAM development files

安装对应的包

```bash
sudo apt-get install libpam0g-dev
```

#### Could not find SELinux development files

安装对应的包

```bash
sudo apt-get install libselinux1-dev
```

#### Could NOT find GnuTLS (missing: GNUTLS_LIBRARY GNUTLS_INCLUDE_DIR) 

安装对应的包

```bash
sudo apt-get install libgnutls28-dev
```

#### No package 'gmp' found

安装对应的包

```bash
sudo apt-get install libgmp3-dev
```

#### No package 'nettle' found

安装对应的包

```bash
sudo apt-get install nettle-dev
```

#### No package 'hogweed' found

安装对应的包

```bash
sudo apt-get install libhogweed5
```

#### No XTest extension.  x0vncserver will be view-only.

安装对应的包

```bash
sudo apt-get install libxtst-dev
```

#### No XFIXES extension.  x0vncserver will not be able to show cursors.

安装对应的包

```bash
sudo apt-get install libxfixes-dev
```

#### No Xrandr extension.  x0vncserver will not be able to resize session.

安装对应的包

```bash
sudo apt-get install libxrandr-dev
```

#### X11_Xi_LIB (ADVANCED)

安装对应的包

```bash
sudo apt-get install libxi-dev
```



### make

#### /usr/bin/msgfmt: cannot locate ITS rules for /tigervnc/vncviewer/org.tigervnc.vncviewer.metainfo.xml.in

安装下面的包

```bash
sudo apt-get install appstream
```

这个包提供了对应的`ITS rules`文件

```bash
dpkg -L appstream | grep meta
/usr/share/gettext/its/metainfo.its
/usr/share/gettext/its/metainfo.loc
/usr/share/metainfo
/usr/share/metainfo/org.freedesktop.appstream.cli.metainfo.xml
```

详细情况可以看这个帖子：https://gitlab.gnome.org/GNOME/evince/-/issues/1260
