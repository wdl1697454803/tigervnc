# tigervnc源码编译

```
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..


-- Checking for module 'pixman-1'
--   No package 'pixman-1' found
sudo apt-get install libpixman-1-dev


Could NOT find FLTK (missing: FLTK_LIBRARIES FLTK_INCLUDE_DIR)
sudo apt-get install libfltk1.3-dev


-- Could NOT find GnuTLS (missing: GNUTLS_LIBRARY GNUTLS_INCLUDE_DIR) 
sudo apt-get install libgnutls28-dev


-- Checking for module 'gmp'
--   No package 'gmp' found
sudo apt-get install libgmp3-dev


-- Checking for module 'nettle>=3.0'
--   No package 'nettle' found
sudo apt-get install nettle-dev


-- Checking for module 'hogweed'
--   No package 'hogweed' found
sudo apt-get install libhogweed5



CMake Warning at unix/x0vncserver/CMakeLists.txt:29 (message):
  No XTest extension.  x0vncserver will be view-only.

sudo apt-get install libxtst-dev



No DAMAGE extension.  x0vncserver will have to use the slower polling
  method.
sudo apt-get install libxdamage-dev
```



```
make

/usr/bin/msgfmt: cannot locate ITS rules for /tigervnc/vncviewer/org.tigervnc.vncviewer.metainfo.xml.in

sudo apt-get install appstream

https://gitlab.gnome.org/GNOME/evince/-/issues/1260

the appstream package provides 
/usr/share/gettext/its/metainfo.its

dpkg -L appstream | grep meta
/usr/share/gettext/its/metainfo.its
/usr/share/gettext/its/metainfo.loc
/usr/share/metainfo
/usr/share/metainfo/org.freedesktop.appstream.cli.metainfo.xml


sudo make install
```





```
vncpasswd 
Password:
Verify:
Would you like to enter a view-only password (y/n)? y
Password:
Verify:



x0vncserver -PasswordFile=/home/kylin/.vnc/passwd
```

