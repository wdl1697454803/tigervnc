```
// 可以配合 -d 和 -i 一起使用。
// 需求：生成 vue 文件夹目录结构树并忽略 node_modules 和 .git，最后将生成的目录结构树导入到 tree.md 文件中。
// 实现：
treer -d vue -e treer.md -i "/node_modules|.git/"


├─BUILDING.txt
├─CMakeLists.txt
├─config.h.in
├─LICENCE.TXT
├─README.rst
├─win
|  ├─CMakeLists.txt
|  ├─resdefs.h.in
|  ├─wm_hooks
|  |    ├─CMakeLists.txt
|  |    ├─resource.h
|  |    ├─wm_hooks.cxx
|  |    ├─wm_hooks.h
|  |    └wm_hooks.rc
|  ├─winvnc
|  |   ├─AddNewClientDialog.h
|  |   ├─buildTime.cxx
|  |   ├─CMakeLists.txt
|  |   ├─connecte.ico
|  |   ├─connected.ico
|  |   ├─ControlPanel.cxx
|  |   ├─ControlPanel.h
|  |   ├─icon_dis.ico
|  |   ├─ListConnInfo.h
|  |   ├─ManagedListener.cxx
|  |   ├─ManagedListener.h
|  |   ├─QueryConnectDialog.cxx
|  |   ├─QueryConnectDialog.h
|  |   ├─resource.h
|  |   ├─STrayIcon.cxx
|  |   ├─STrayIcon.h
|  |   ├─VNCServerService.cxx
|  |   ├─VNCServerService.h
|  |   ├─VNCServerWin32.cxx
|  |   ├─VNCServerWin32.h
|  |   ├─winvnc.bmp
|  |   ├─winvnc.cxx
|  |   ├─winvnc.ico
|  |   ├─winvnc.rc
|  |   ├─winvnc4.exe.manifest
|  |   └winvnc4.exe.manifest64
|  ├─vncconfig
|  |     ├─Authentication.h
|  |     ├─CMakeLists.txt
|  |     ├─Connections.h
|  |     ├─Desktop.h
|  |     ├─Hooking.h
|  |     ├─Inputs.h
|  |     ├─Legacy.cxx
|  |     ├─Legacy.h
|  |     ├─PasswordDialog.cxx
|  |     ├─PasswordDialog.h
|  |     ├─resource.h
|  |     ├─Sharing.h
|  |     ├─vncconfig.cxx
|  |     ├─vncconfig.exe.manifest
|  |     ├─vncconfig.exe.manifest64
|  |     ├─vncconfig.ico
|  |     └vncconfig.rc
|  ├─rfb_win32
|  |     ├─AboutDialog.cxx
|  |     ├─AboutDialog.h
|  |     ├─BitmapInfo.h
|  |     ├─CleanDesktop.cxx
|  |     ├─CleanDesktop.h
|  |     ├─Clipboard.cxx
|  |     ├─Clipboard.h
|  |     ├─CMakeLists.txt
|  |     ├─CompatibleBitmap.h
|  |     ├─ComputerName.h
|  |     ├─CurrentUser.cxx
|  |     ├─CurrentUser.h
|  |     ├─DeviceContext.cxx
|  |     ├─DeviceContext.h
|  |     ├─DeviceFrameBuffer.cxx
|  |     ├─DeviceFrameBuffer.h
|  |     ├─Dialog.cxx
|  |     ├─Dialog.h
|  |     ├─DIBSectionBuffer.cxx
|  |     ├─DIBSectionBuffer.h
|  |     ├─EventManager.cxx
|  |     ├─EventManager.h
|  |     ├─Handle.h
|  |     ├─IconInfo.h
|  |     ├─IntervalTimer.h
|  |     ├─keymap.h
|  |     ├─LaunchProcess.cxx
|  |     ├─LaunchProcess.h
|  |     ├─ListViewControl.cxx
|  |     ├─ListViewControl.h
|  |     ├─LocalMem.h
|  |     ├─ModuleFileName.h
|  |     ├─MonitorInfo.cxx
|  |     ├─MonitorInfo.h
|  |     ├─MsgBox.h
|  |     ├─MsgWindow.cxx
|  |     ├─MsgWindow.h
|  |     ├─RegConfig.cxx
|  |     ├─RegConfig.h
|  |     ├─Registry.cxx
|  |     ├─Registry.h
|  |     ├─resource.h
|  |     ├─SDisplay.cxx
|  |     ├─SDisplay.h
|  |     ├─SDisplayCorePolling.cxx
|  |     ├─SDisplayCorePolling.h
|  |     ├─SDisplayCoreWMHooks.cxx
|  |     ├─SDisplayCoreWMHooks.h
|  |     ├─Security.cxx
|  |     ├─Security.h
|  |     ├─SecurityPage.cxx
|  |     ├─SecurityPage.h
|  |     ├─Service.cxx
|  |     ├─Service.h
|  |     ├─SInput.cxx
|  |     ├─SInput.h
|  |     ├─SocketManager.cxx
|  |     ├─SocketManager.h
|  |     ├─TrayIcon.h
|  |     ├─TsSessions.cxx
|  |     ├─TsSessions.h
|  |     ├─Win32Util.cxx
|  |     ├─Win32Util.h
|  |     ├─WMCursor.cxx
|  |     ├─WMCursor.h
|  |     ├─WMHooks.cxx
|  |     ├─WMHooks.h
|  |     ├─WMNotifier.cxx
|  |     ├─WMNotifier.h
|  |     ├─WMPoller.cxx
|  |     ├─WMPoller.h
|  |     ├─WMShatter.cxx
|  |     ├─WMShatter.h
|  |     ├─WMWindowCopyRect.cxx
|  |     └WMWindowCopyRect.h
|  ├─logmessages
|  |      ├─messages.h
|  |      ├─messages.mc
|  |      └messages.rc
├─vncviewer
|     ├─BaseTouchHandler.cxx
|     ├─BaseTouchHandler.h
|     ├─CConn.cxx
|     ├─CConn.h
|     ├─CMakeLists.txt
|     ├─cocoa.h
|     ├─cocoa.mm
|     ├─DesktopWindow.cxx
|     ├─DesktopWindow.h
|     ├─EmulateMB.cxx
|     ├─EmulateMB.h
|     ├─GestureEvent.h
|     ├─GestureHandler.cxx
|     ├─GestureHandler.h
|     ├─gettext.h
|     ├─i18n.h
|     ├─keysym2ucs.c
|     ├─keysym2ucs.h
|     ├─menukey.cxx
|     ├─menukey.h
|     ├─MonitorIndicesParameter.cxx
|     ├─MonitorIndicesParameter.h
|     ├─OptionsDialog.cxx
|     ├─OptionsDialog.h
|     ├─org.tigervnc.vncviewer.metainfo.xml.in
|     ├─osx_to_qnum.c
|     ├─parameters.cxx
|     ├─parameters.h
|     ├─PlatformPixelBuffer.cxx
|     ├─PlatformPixelBuffer.h
|     ├─resource.h
|     ├─ServerDialog.cxx
|     ├─ServerDialog.h
|     ├─Surface.cxx
|     ├─Surface.h
|     ├─Surface_OSX.cxx
|     ├─Surface_Win32.cxx
|     ├─Surface_X11.cxx
|     ├─touch.cxx
|     ├─touch.h
|     ├─UserDialog.cxx
|     ├─UserDialog.h
|     ├─Viewport.cxx
|     ├─Viewport.h
|     ├─vncviewer.cxx
|     ├─vncviewer.desktop.in.in
|     ├─vncviewer.h
|     ├─vncviewer.man
|     ├─vncviewer.rc.in
|     ├─win32.c
|     ├─win32.h
|     ├─Win32TouchHandler.cxx
|     ├─Win32TouchHandler.h
|     ├─XInputTouchHandler.cxx
|     ├─XInputTouchHandler.h
|     ├─xkb_to_qnum.c
|     ├─metainfo
|     |    ├─tigervnc-connection-linux.jpg
|     |    ├─tigervnc-connection-macos.jpg
|     |    └tigervnc-connection-windows.jpg
|     ├─fltk
|     |  ├─Fl_Monitor_Arrangement.cxx
|     |  ├─Fl_Monitor_Arrangement.h
|     |  ├─Fl_Navigation.cxx
|     |  ├─Fl_Navigation.h
|     |  ├─layout.h
|     |  ├─theme.cxx
|     |  ├─theme.h
|     |  └util.h
├─unix
|  ├─CMakeLists.txt
|  ├─xserver116.patch
|  ├─xserver117.patch
|  ├─xserver118.patch
|  ├─xserver119.patch
|  ├─xserver120.patch
|  ├─xserver21.1.1.patch
|  ├─xserver
|  |    ├─hw
|  |    | ├─vnc
|  |    | |  ├─buildtime.c
|  |    | |  ├─Makefile.am
|  |    | |  ├─qnum_to_xorgevdev.c
|  |    | |  ├─qnum_to_xorgkbd.c
|  |    | |  ├─RandrGlue.c
|  |    | |  ├─RFBGlue.cc
|  |    | |  ├─RFBGlue.h
|  |    | |  ├─vncBlockHandler.c
|  |    | |  ├─vncBlockHandler.h
|  |    | |  ├─vncExt.c
|  |    | |  ├─vncExtInit.cc
|  |    | |  ├─vncExtInit.h
|  |    | |  ├─vncHooks.c
|  |    | |  ├─vncHooks.h
|  |    | |  ├─vncInput.c
|  |    | |  ├─vncInput.h
|  |    | |  ├─vncInputXKB.c
|  |    | |  ├─vncModule.c
|  |    | |  ├─vncSelection.c
|  |    | |  ├─vncSelection.h
|  |    | |  ├─xorg-version.h
|  |    | |  ├─XorgGlue.c
|  |    | |  ├─XorgGlue.h
|  |    | |  ├─XserverDesktop.cc
|  |    | |  ├─XserverDesktop.h
|  |    | |  ├─xvnc.c
|  |    | |  └Xvnc.man
|  ├─x0vncserver
|  |      ├─buildtime.c
|  |      ├─CMakeLists.txt
|  |      ├─Geometry.cxx
|  |      ├─Geometry.h
|  |      ├─Image.cxx
|  |      ├─Image.h
|  |      ├─PollingManager.cxx
|  |      ├─PollingManager.h
|  |      ├─PollingScheduler.cxx
|  |      ├─PollingScheduler.h
|  |      ├─qnum_to_xorgevdev.c
|  |      ├─qnum_to_xorgkbd.c
|  |      ├─RandrGlue.c
|  |      ├─TimeMillis.cxx
|  |      ├─TimeMillis.h
|  |      ├─x0vncserver.cxx
|  |      ├─x0vncserver.man
|  |      ├─XDesktop.cxx
|  |      ├─XDesktop.h
|  |      ├─XPixelBuffer.cxx
|  |      └XPixelBuffer.h
|  ├─vncserver
|  |     ├─CMakeLists.txt
|  |     ├─HOWTO.md
|  |     ├─tigervnc.pam
|  |     ├─vncserver-config-defaults
|  |     ├─vncserver-config-mandatory
|  |     ├─vncserver.in
|  |     ├─vncserver.man
|  |     ├─vncserver.users
|  |     ├─vncserver@.service.in
|  |     ├─vncsession-start.in
|  |     ├─vncsession.c
|  |     ├─vncsession.man.in
|  |     ├─selinux
|  |     |    ├─Makefile
|  |     |    ├─vncsession.fc
|  |     |    ├─vncsession.if
|  |     |    └vncsession.te
|  ├─vncpasswd
|  |     ├─CMakeLists.txt
|  |     ├─vncpasswd.cxx
|  |     └vncpasswd.man
|  ├─vncconfig
|  |     ├─buildtime.c
|  |     ├─CMakeLists.txt
|  |     ├─QueryConnectDialog.cxx
|  |     ├─QueryConnectDialog.h
|  |     ├─vncconfig.cxx
|  |     ├─vncconfig.man
|  |     ├─vncExt.c
|  |     └vncExt.h
|  ├─tx
|  | ├─CMakeLists.txt
|  | ├─TXButton.h
|  | ├─TXCheckbox.h
|  | ├─TXDialog.h
|  | ├─TXLabel.h
|  | ├─TXWindow.cxx
|  | └TXWindow.h
|  ├─common
|  |   ├─CMakeLists.txt
|  |   ├─randr.cxx
|  |   ├─RandrGlue.h
|  |   └unixcommon.h
├─tests
|   ├─CMakeLists.txt
|   ├─unit
|   |  ├─CMakeLists.txt
|   |  ├─conv.cxx
|   |  ├─convertlf.cxx
|   |  ├─emulatemb.cxx
|   |  ├─gesturehandler.cxx
|   |  ├─hostport.cxx
|   |  ├─pixelformat.cxx
|   |  └unicode.cxx
|   ├─perf
|   |  ├─CMakeLists.txt
|   |  ├─convperf.cxx
|   |  ├─decperf.cxx
|   |  ├─encperf.cxx
|   |  ├─fbperf.cxx
|   |  ├─util.cxx
|   |  ├─util.h
|   |  ├─results
|   |  |    ├─notrans
|   |  |    |    ├─armhf.csv
|   |  |    |    ├─i386.csv
|   |  |    |    ├─README
|   |  |    |    └x86_64.csv
|   |  |    ├─multicore
|   |  |    |     ├─multicore.ods
|   |  |    |     └README
├─release
|    ├─CMakeLists.txt
|    ├─Info.plist.in
|    ├─makemacapp.in
|    ├─maketarball.in
|    ├─tigervnc.iss.in
|    └winvnc.iss.in
├─po
| ├─bg.po
| ├─CMakeLists.txt
| ├─cs.po
| ├─da.po
| ├─de.po
| ├─el.po
| ├─eo.po
| ├─es.po
| ├─fi.po
| ├─fr.po
| ├─fur.po
| ├─he.po
| ├─hu.po
| ├─id.po
| ├─it.po
| ├─ka.po
| ├─ko.po
| ├─LINGUAS
| ├─nl.po
| ├─pl.po
| ├─pt_BR.po
| ├─ro.po
| ├─ru.po
| ├─sk.po
| ├─sr.po
| ├─sv.po
| ├─tigervnc.pot
| ├─tr.po
| ├─uk.po
| ├─vi.po
| ├─zh_CN.po
| └zh_TW.po
├─media
|   ├─CMakeLists.txt
|   ├─insecure.svg
|   ├─insecure.xpm
|   ├─secure.svg
|   ├─secure.xpm
|   ├─tigervnc.svg
|   ├─tigervnc_16.svg
|   ├─tigervnc_22.svg
|   ├─tigervnc_24.svg
|   ├─tigervnc_32.svg
|   ├─tigervnc_48.svg
|   ├─icons
|   |   ├─tigervnc.icns
|   |   ├─tigervnc.ico
|   |   ├─tigervnc.svg
|   |   ├─tigervnc_128.png
|   |   ├─tigervnc_16.png
|   |   ├─tigervnc_22.png
|   |   ├─tigervnc_24.png
|   |   ├─tigervnc_32.png
|   |   ├─tigervnc_48.png
|   |   └tigervnc_64.png
├─java
|  ├─CMakeLists.txt
|  ├─com
|  |  ├─tigervnc
|  |  |    ├─vncviewer
|  |  |    |     ├─CConn.java
|  |  |    |     ├─ClipboardDialog.java
|  |  |    |     ├─DesktopWindow.java
|  |  |    |     ├─Dialog.java
|  |  |    |     ├─ExtProcess.java
|  |  |    |     ├─FileUtils.java
|  |  |    |     ├─insecure.png
|  |  |    |     ├─JavaPixelBuffer.java
|  |  |    |     ├─KeyMap.java
|  |  |    |     ├─LICENCE.TXT
|  |  |    |     ├─MANIFEST.MF
|  |  |    |     ├─MenuKey.java
|  |  |    |     ├─OptionsDialog.java
|  |  |    |     ├─Parameters.java
|  |  |    |     ├─PasswdDialog.java
|  |  |    |     ├─PlatformPixelBuffer.java
|  |  |    |     ├─README
|  |  |    |     ├─secure.png
|  |  |    |     ├─ServerDialog.java
|  |  |    |     ├─tigervnc.ico
|  |  |    |     ├─tigervnc.png
|  |  |    |     ├─timestamp.in
|  |  |    |     ├─Tunnel.java
|  |  |    |     ├─UserDialog.java
|  |  |    |     ├─UserPreferences.java
|  |  |    |     ├─Viewport.java
|  |  |    |     └VncViewer.java
|  |  |    ├─rfb
|  |  |    |  ├─AliasParameter.java
|  |  |    |  ├─AuthFailureException.java
|  |  |    |  ├─BoolParameter.java
|  |  |    |  ├─CConnection.java
|  |  |    |  ├─CMsgHandler.java
|  |  |    |  ├─CMsgReader.java
|  |  |    |  ├─CMsgWriter.java
|  |  |    |  ├─Configuration.java
|  |  |    |  ├─ConnFailedException.java
|  |  |    |  ├─CopyRectDecoder.java
|  |  |    |  ├─CSecurity.java
|  |  |    |  ├─CSecurityIdent.java
|  |  |    |  ├─CSecurityNone.java
|  |  |    |  ├─CSecurityPlain.java
|  |  |    |  ├─CSecurityRSAAES.java
|  |  |    |  ├─CSecurityStack.java
|  |  |    |  ├─CSecurityTLS.java
|  |  |    |  ├─CSecurityVeNCrypt.java
|  |  |    |  ├─CSecurityVncAuth.java
|  |  |    |  ├─Cursor.java
|  |  |    |  ├─DecodeManager.java
|  |  |    |  ├─Decoder.java
|  |  |    |  ├─DesCipher.java
|  |  |    |  ├─Encoder.java
|  |  |    |  ├─Encodings.java
|  |  |    |  ├─Exception.java
|  |  |    |  ├─fenceTypes.java
|  |  |    |  ├─FullFramePixelBuffer.java
|  |  |    |  ├─Hextile.java
|  |  |    |  ├─HextileDecoder.java
|  |  |    |  ├─Hostname.java
|  |  |    |  ├─IntParameter.java
|  |  |    |  ├─JpegCompressor.java
|  |  |    |  ├─JpegDecompressor.java
|  |  |    |  ├─Keysym2ucs.java
|  |  |    |  ├─Keysymdef.java
|  |  |    |  ├─LogWriter.java
|  |  |    |  ├─ManagedPixelBuffer.java
|  |  |    |  ├─ModifiablePixelBuffer.java
|  |  |    |  ├─MsgTypes.java
|  |  |    |  ├─PixelBuffer.java
|  |  |    |  ├─PixelFormat.java
|  |  |    |  ├─Point.java
|  |  |    |  ├─RawDecoder.java
|  |  |    |  ├─Rect.java
|  |  |    |  ├─Region.java
|  |  |    |  ├─RREDecoder.java
|  |  |    |  ├─Screen.java
|  |  |    |  ├─ScreenSet.java
|  |  |    |  ├─screenTypes.java
|  |  |    |  ├─Security.java
|  |  |    |  ├─SecurityClient.java
|  |  |    |  ├─ServerParams.java
|  |  |    |  ├─StringParameter.java
|  |  |    |  ├─TightDecoder.java
|  |  |    |  ├─UserMsgBox.java
|  |  |    |  ├─UserPasswdGetter.java
|  |  |    |  ├─VncAuth.java
|  |  |    |  ├─VoidParameter.java
|  |  |    |  └ZRLEDecoder.java
|  |  |    ├─rdr
|  |  |    |  ├─AESEAXCipher.java
|  |  |    |  ├─AESInStream.java
|  |  |    |  ├─AESOutStream.java
|  |  |    |  ├─EndOfStream.java
|  |  |    |  ├─Exception.java
|  |  |    |  ├─FdInStream.java
|  |  |    |  ├─FdInStreamBlockCallback.java
|  |  |    |  ├─FdOutStream.java
|  |  |    |  ├─InStream.java
|  |  |    |  ├─MemInStream.java
|  |  |    |  ├─MemOutStream.java
|  |  |    |  ├─OutStream.java
|  |  |    |  ├─SystemException.java
|  |  |    |  ├─TimedOut.java
|  |  |    |  ├─TLSException.java
|  |  |    |  ├─TLSInStream.java
|  |  |    |  ├─TLSOutStream.java
|  |  |    |  ├─WarningException.java
|  |  |    |  └ZlibInStream.java
|  |  |    ├─network
|  |  |    |    ├─FileDescriptor.java
|  |  |    |    ├─Socket.java
|  |  |    |    ├─SocketDescriptor.java
|  |  |    |    ├─SocketException.java
|  |  |    |    ├─SocketListener.java
|  |  |    |    ├─SSLEngineManager.java
|  |  |    |    ├─TcpListener.java
|  |  |    |    └TcpSocket.java
|  |  ├─jcraft
|  |  |   ├─jzlib
|  |  |   |   ├─Adler32.java
|  |  |   |   ├─ChangeLog
|  |  |   |   ├─Checksum.java
|  |  |   |   ├─CRC32.java
|  |  |   |   ├─Deflate.java
|  |  |   |   ├─Deflater.java
|  |  |   |   ├─DeflaterOutputStream.java
|  |  |   |   ├─GZIPException.java
|  |  |   |   ├─GZIPHeader.java
|  |  |   |   ├─GZIPInputStream.java
|  |  |   |   ├─GZIPOutputStream.java
|  |  |   |   ├─InfBlocks.java
|  |  |   |   ├─InfCodes.java
|  |  |   |   ├─Inflate.java
|  |  |   |   ├─Inflater.java
|  |  |   |   ├─InflaterInputStream.java
|  |  |   |   ├─InfTree.java
|  |  |   |   ├─JZlib.java
|  |  |   |   ├─LICENSE.txt
|  |  |   |   ├─README
|  |  |   |   ├─StaticTree.java
|  |  |   |   ├─Tree.java
|  |  |   |   ├─ZInputStream.java
|  |  |   |   ├─ZOutputStream.java
|  |  |   |   ├─ZStream.java
|  |  |   |   └ZStreamException.java
|  |  |   ├─jsch
|  |  |   |  ├─Buffer.java
|  |  |   |  ├─ChangeLog
|  |  |   |  ├─Channel.java
|  |  |   |  ├─ChannelAgentForwarding.java
|  |  |   |  ├─ChannelDirectTCPIP.java
|  |  |   |  ├─ChannelExec.java
|  |  |   |  ├─ChannelForwardedTCPIP.java
|  |  |   |  ├─ChannelSession.java
|  |  |   |  ├─ChannelSftp.java
|  |  |   |  ├─ChannelShell.java
|  |  |   |  ├─ChannelSubsystem.java
|  |  |   |  ├─ChannelX11.java
|  |  |   |  ├─Cipher.java
|  |  |   |  ├─CipherNone.java
|  |  |   |  ├─Compression.java
|  |  |   |  ├─ConfigRepository.java
|  |  |   |  ├─DH.java
|  |  |   |  ├─DHEC256.java
|  |  |   |  ├─DHEC384.java
|  |  |   |  ├─DHEC521.java
|  |  |   |  ├─DHECN.java
|  |  |   |  ├─DHG1.java
|  |  |   |  ├─DHG14.java
|  |  |   |  ├─DHGEX.java
|  |  |   |  ├─DHGEX256.java
|  |  |   |  ├─ECDH.java
|  |  |   |  ├─ForwardedTCPIPDaemon.java
|  |  |   |  ├─GSSContext.java
|  |  |   |  ├─HASH.java
|  |  |   |  ├─HostKey.java
|  |  |   |  ├─HostKeyRepository.java
|  |  |   |  ├─Identity.java
|  |  |   |  ├─IdentityFile.java
|  |  |   |  ├─IdentityRepository.java
|  |  |   |  ├─IO.java
|  |  |   |  ├─JSch.java
|  |  |   |  ├─JSchAuthCancelException.java
|  |  |   |  ├─JSchException.java
|  |  |   |  ├─JSchPartialAuthException.java
|  |  |   |  ├─KeyExchange.java
|  |  |   |  ├─KeyPair.java
|  |  |   |  ├─KeyPairDSA.java
|  |  |   |  ├─KeyPairECDSA.java
|  |  |   |  ├─KeyPairGenDSA.java
|  |  |   |  ├─KeyPairGenECDSA.java
|  |  |   |  ├─KeyPairGenRSA.java
|  |  |   |  ├─KeyPairPKCS8.java
|  |  |   |  ├─KeyPairRSA.java
|  |  |   |  ├─KnownHosts.java
|  |  |   |  ├─LICENSE.txt
|  |  |   |  ├─LocalIdentityRepository.java
|  |  |   |  ├─Logger.java
|  |  |   |  ├─MAC.java
|  |  |   |  ├─OpenSSHConfig.java
|  |  |   |  ├─Packet.java
|  |  |   |  ├─PBKDF.java
|  |  |   |  ├─PortWatcher.java
|  |  |   |  ├─Proxy.java
|  |  |   |  ├─ProxyHTTP.java
|  |  |   |  ├─ProxySOCKS4.java
|  |  |   |  ├─ProxySOCKS5.java
|  |  |   |  ├─Random.java
|  |  |   |  ├─README
|  |  |   |  ├─Request.java
|  |  |   |  ├─RequestAgentForwarding.java
|  |  |   |  ├─RequestEnv.java
|  |  |   |  ├─RequestExec.java
|  |  |   |  ├─RequestPtyReq.java
|  |  |   |  ├─RequestSftp.java
|  |  |   |  ├─RequestShell.java
|  |  |   |  ├─RequestSignal.java
|  |  |   |  ├─RequestSubsystem.java
|  |  |   |  ├─RequestWindowChange.java
|  |  |   |  ├─RequestX11.java
|  |  |   |  ├─ServerSocketFactory.java
|  |  |   |  ├─Session.java
|  |  |   |  ├─SftpATTRS.java
|  |  |   |  ├─SftpException.java
|  |  |   |  ├─SftpProgressMonitor.java
|  |  |   |  ├─SftpStatVFS.java
|  |  |   |  ├─Signature.java
|  |  |   |  ├─SignatureDSA.java
|  |  |   |  ├─SignatureECDSA.java
|  |  |   |  ├─SignatureRSA.java
|  |  |   |  ├─SocketFactory.java
|  |  |   |  ├─UIKeyboardInteractive.java
|  |  |   |  ├─UserAuth.java
|  |  |   |  ├─UserAuthGSSAPIWithMIC.java
|  |  |   |  ├─UserAuthKeyboardInteractive.java
|  |  |   |  ├─UserAuthNone.java
|  |  |   |  ├─UserAuthPassword.java
|  |  |   |  ├─UserAuthPublicKey.java
|  |  |   |  ├─UserInfo.java
|  |  |   |  ├─Util.java
|  |  |   |  ├─jgss
|  |  |   |  |  └GSSContextKrb5.java
|  |  |   |  ├─jcraft
|  |  |   |  |   ├─Compression.java
|  |  |   |  |   ├─HMAC.java
|  |  |   |  |   ├─HMACMD5.java
|  |  |   |  |   ├─HMACMD596.java
|  |  |   |  |   ├─HMACSHA1.java
|  |  |   |  |   └HMACSHA196.java
|  |  |   |  ├─jce
|  |  |   |  |  ├─AES128CBC.java
|  |  |   |  |  ├─AES128CTR.java
|  |  |   |  |  ├─AES192CBC.java
|  |  |   |  |  ├─AES192CTR.java
|  |  |   |  |  ├─AES256CBC.java
|  |  |   |  |  ├─AES256CTR.java
|  |  |   |  |  ├─ARCFOUR.java
|  |  |   |  |  ├─ARCFOUR128.java
|  |  |   |  |  ├─ARCFOUR256.java
|  |  |   |  |  ├─BlowfishCBC.java
|  |  |   |  |  ├─DH.java
|  |  |   |  |  ├─ECDH256.java
|  |  |   |  |  ├─ECDH384.java
|  |  |   |  |  ├─ECDH521.java
|  |  |   |  |  ├─ECDHN.java
|  |  |   |  |  ├─HMAC.java
|  |  |   |  |  ├─HMACMD5.java
|  |  |   |  |  ├─HMACMD596.java
|  |  |   |  |  ├─HMACSHA1.java
|  |  |   |  |  ├─HMACSHA196.java
|  |  |   |  |  ├─HMACSHA256.java
|  |  |   |  |  ├─HMACSHA512.java
|  |  |   |  |  ├─KeyPairGenDSA.java
|  |  |   |  |  ├─KeyPairGenECDSA.java
|  |  |   |  |  ├─KeyPairGenRSA.java
|  |  |   |  |  ├─MD5.java
|  |  |   |  |  ├─PBKDF.java
|  |  |   |  |  ├─Random.java
|  |  |   |  |  ├─SHA1.java
|  |  |   |  |  ├─SHA256.java
|  |  |   |  |  ├─SHA384.java
|  |  |   |  |  ├─SHA512.java
|  |  |   |  |  ├─SignatureDSA.java
|  |  |   |  |  ├─SignatureECDSA.java
|  |  |   |  |  ├─SignatureRSA.java
|  |  |   |  |  ├─TripleDESCBC.java
|  |  |   |  |  └TripleDESCTR.java
|  ├─cmake
|  |   └SignJar.cmake
├─doc
|  └keyboard-test.txt
├─contrib
|    ├─packages
|    |    ├─rpm
|    |    |  ├─el9
|    |    |  |  ├─SPECS
|    |    |  |  |   └tigervnc.spec
|    |    |  |  ├─SOURCES
|    |    |  |  |    └10-libvnc.conf
|    |    |  ├─el8
|    |    |  |  ├─SPECS
|    |    |  |  |   └tigervnc.spec
|    |    |  |  ├─SOURCES
|    |    |  |  |    └10-libvnc.conf
|    |    |  ├─el7
|    |    |  |  ├─SPECS
|    |    |  |  |   └tigervnc.spec
|    |    |  |  ├─SOURCES
|    |    |  |  |    └10-libvnc.conf
|    |    ├─deb
|    |    |  ├─ubuntu-jammy
|    |    |  |      ├─debian
|    |    |  |      |   ├─changelog
|    |    |  |      |   ├─compat
|    |    |  |      |   ├─control
|    |    |  |      |   ├─copyright
|    |    |  |      |   ├─rules
|    |    |  |      |   ├─tigervncserver.postinst.in
|    |    |  |      |   ├─tigervncserver.prerm
|    |    |  |      |   ├─xtigervncviewer.menu
|    |    |  |      |   ├─xtigervncviewer.postinst
|    |    |  |      |   ├─xtigervncviewer.prerm
|    |    |  |      |   ├─xorg-source-patches
|    |    |  |      |   |          ├─516_tigervnc-xorg-manpages.patch
|    |    |  |      |   |          └debian_libtool.patch
|    |    |  |      |   ├─source
|    |    |  |      |   |   └format
|    |    |  ├─ubuntu-focal
|    |    |  |      ├─debian
|    |    |  |      |   ├─changelog
|    |    |  |      |   ├─compat
|    |    |  |      |   ├─control
|    |    |  |      |   ├─copyright
|    |    |  |      |   ├─rules
|    |    |  |      |   ├─tigervncserver.postinst.in
|    |    |  |      |   ├─tigervncserver.prerm
|    |    |  |      |   ├─xtigervncviewer.menu
|    |    |  |      |   ├─xtigervncviewer.postinst
|    |    |  |      |   ├─xtigervncviewer.prerm
|    |    |  |      |   ├─xorg-source-patches
|    |    |  |      |   |          ├─516_tigervnc-xorg-manpages.patch
|    |    |  |      |   |          └debian_libtool.patch
|    |    |  |      |   ├─source
|    |    |  |      |   |   └format
|    |    |  ├─ubuntu-bionic
|    |    |  |       ├─debian
|    |    |  |       |   ├─changelog
|    |    |  |       |   ├─compat
|    |    |  |       |   ├─control
|    |    |  |       |   ├─copyright
|    |    |  |       |   ├─rules
|    |    |  |       |   ├─tigervncserver.postinst.in
|    |    |  |       |   ├─tigervncserver.prerm
|    |    |  |       |   ├─xtigervncviewer.menu
|    |    |  |       |   ├─xtigervncviewer.postinst
|    |    |  |       |   ├─xtigervncviewer.prerm
|    |    |  |       |   ├─xorg-source-patches
|    |    |  |       |   |          ├─516_tigervnc-xorg-manpages.patch
|    |    |  |       |   |          └debian_libtool.patch
|    |    |  |       |   ├─source
|    |    |  |       |   |   └format
├─common
|   ├─CMakeLists.txt
|   ├─rfb
|   |  ├─Blacklist.cxx
|   |  ├─Blacklist.h
|   |  ├─CConnection.cxx
|   |  ├─CConnection.h
|   |  ├─ClientParams.cxx
|   |  ├─ClientParams.h
|   |  ├─clipboardTypes.h
|   |  ├─CMakeLists.txt
|   |  ├─CMsgHandler.cxx
|   |  ├─CMsgHandler.h
|   |  ├─CMsgReader.cxx
|   |  ├─CMsgReader.h
|   |  ├─CMsgWriter.cxx
|   |  ├─CMsgWriter.h
|   |  ├─ComparingUpdateTracker.cxx
|   |  ├─ComparingUpdateTracker.h
|   |  ├─Configuration.cxx
|   |  ├─Configuration.h
|   |  ├─Congestion.cxx
|   |  ├─Congestion.h
|   |  ├─CopyRectDecoder.cxx
|   |  ├─CopyRectDecoder.h
|   |  ├─CSecurity.h
|   |  ├─CSecurityDH.cxx
|   |  ├─CSecurityDH.h
|   |  ├─CSecurityMSLogonII.cxx
|   |  ├─CSecurityMSLogonII.h
|   |  ├─CSecurityNone.h
|   |  ├─CSecurityPlain.cxx
|   |  ├─CSecurityPlain.h
|   |  ├─CSecurityRSAAES.cxx
|   |  ├─CSecurityRSAAES.h
|   |  ├─CSecurityStack.cxx
|   |  ├─CSecurityStack.h
|   |  ├─CSecurityTLS.cxx
|   |  ├─CSecurityTLS.h
|   |  ├─CSecurityVeNCrypt.cxx
|   |  ├─CSecurityVeNCrypt.h
|   |  ├─CSecurityVncAuth.cxx
|   |  ├─CSecurityVncAuth.h
|   |  ├─Cursor.cxx
|   |  ├─Cursor.h
|   |  ├─d3des.c
|   |  ├─d3des.h
|   |  ├─DecodeManager.cxx
|   |  ├─DecodeManager.h
|   |  ├─Decoder.cxx
|   |  ├─Decoder.h
|   |  ├─EncodeManager.cxx
|   |  ├─EncodeManager.h
|   |  ├─Encoder.cxx
|   |  ├─Encoder.h
|   |  ├─encodings.cxx
|   |  ├─encodings.h
|   |  ├─Exception.h
|   |  ├─fenceTypes.h
|   |  ├─H264Decoder.cxx
|   |  ├─H264Decoder.h
|   |  ├─H264DecoderContext.cxx
|   |  ├─H264DecoderContext.h
|   |  ├─H264LibavDecoderContext.cxx
|   |  ├─H264LibavDecoderContext.h
|   |  ├─H264WinDecoderContext.cxx
|   |  ├─H264WinDecoderContext.h
|   |  ├─hextileConstants.h
|   |  ├─HextileDecoder.cxx
|   |  ├─HextileDecoder.h
|   |  ├─HextileEncoder.cxx
|   |  ├─HextileEncoder.h
|   |  ├─Hostname.h
|   |  ├─InputHandler.h
|   |  ├─JpegCompressor.cxx
|   |  ├─JpegCompressor.h
|   |  ├─JpegDecompressor.cxx
|   |  ├─JpegDecompressor.h
|   |  ├─KeyRemapper.cxx
|   |  ├─KeyRemapper.h
|   |  ├─keysymdef.h
|   |  ├─ledStates.h
|   |  ├─Logger.cxx
|   |  ├─Logger.h
|   |  ├─Logger_file.cxx
|   |  ├─Logger_file.h
|   |  ├─Logger_stdio.cxx
|   |  ├─Logger_stdio.h
|   |  ├─Logger_syslog.cxx
|   |  ├─Logger_syslog.h
|   |  ├─LogWriter.cxx
|   |  ├─LogWriter.h
|   |  ├─msgTypes.h
|   |  ├─obfuscate.cxx
|   |  ├─obfuscate.h
|   |  ├─Palette.h
|   |  ├─pam.c
|   |  ├─pam.h
|   |  ├─PixelBuffer.cxx
|   |  ├─PixelBuffer.h
|   |  ├─PixelFormat.cxx
|   |  ├─PixelFormat.h
|   |  ├─PixelFormat.inl
|   |  ├─qemuTypes.h
|   |  ├─RawDecoder.cxx
|   |  ├─RawDecoder.h
|   |  ├─RawEncoder.cxx
|   |  ├─RawEncoder.h
|   |  ├─Rect.h
|   |  ├─Region.cxx
|   |  ├─Region.h
|   |  ├─RREDecoder.cxx
|   |  ├─RREDecoder.h
|   |  ├─RREEncoder.cxx
|   |  ├─RREEncoder.h
|   |  ├─ScaleFilters.cxx
|   |  ├─ScaleFilters.h
|   |  ├─SConnection.cxx
|   |  ├─SConnection.h
|   |  ├─ScreenSet.h
|   |  ├─screenTypes.h
|   |  ├─SDesktop.h
|   |  ├─Security.cxx
|   |  ├─Security.h
|   |  ├─SecurityClient.cxx
|   |  ├─SecurityClient.h
|   |  ├─SecurityServer.cxx
|   |  ├─SecurityServer.h
|   |  ├─ServerCore.cxx
|   |  ├─ServerCore.h
|   |  ├─ServerParams.cxx
|   |  ├─ServerParams.h
|   |  ├─SMsgHandler.cxx
|   |  ├─SMsgHandler.h
|   |  ├─SMsgReader.cxx
|   |  ├─SMsgReader.h
|   |  ├─SMsgWriter.cxx
|   |  ├─SMsgWriter.h
|   |  ├─SSecurity.h
|   |  ├─SSecurityNone.h
|   |  ├─SSecurityPlain.cxx
|   |  ├─SSecurityPlain.h
|   |  ├─SSecurityRSAAES.cxx
|   |  ├─SSecurityRSAAES.h
|   |  ├─SSecurityStack.cxx
|   |  ├─SSecurityStack.h
|   |  ├─SSecurityTLS.cxx
|   |  ├─SSecurityTLS.h
|   |  ├─SSecurityVeNCrypt.cxx
|   |  ├─SSecurityVeNCrypt.h
|   |  ├─SSecurityVncAuth.cxx
|   |  ├─SSecurityVncAuth.h
|   |  ├─TightConstants.h
|   |  ├─TightDecoder.cxx
|   |  ├─TightDecoder.h
|   |  ├─TightEncoder.cxx
|   |  ├─TightEncoder.h
|   |  ├─TightJPEGEncoder.cxx
|   |  ├─TightJPEGEncoder.h
|   |  ├─Timer.cxx
|   |  ├─Timer.h
|   |  ├─UnixPasswordValidator.cxx
|   |  ├─UnixPasswordValidator.h
|   |  ├─UpdateTracker.cxx
|   |  ├─UpdateTracker.h
|   |  ├─UserMsgBox.h
|   |  ├─UserPasswdGetter.h
|   |  ├─util.cxx
|   |  ├─util.h
|   |  ├─VNCSConnectionST.cxx
|   |  ├─VNCSConnectionST.h
|   |  ├─VNCServer.h
|   |  ├─VNCServerST.cxx
|   |  ├─VNCServerST.h
|   |  ├─WinPasswdValidator.cxx
|   |  ├─WinPasswdValidator.h
|   |  ├─XF86keysym.h
|   |  ├─ZRLEDecoder.cxx
|   |  ├─ZRLEDecoder.h
|   |  ├─ZRLEEncoder.cxx
|   |  └ZRLEEncoder.h
|   ├─rdr
|   |  ├─AESInStream.cxx
|   |  ├─AESInStream.h
|   |  ├─AESOutStream.cxx
|   |  ├─AESOutStream.h
|   |  ├─BufferedInStream.cxx
|   |  ├─BufferedInStream.h
|   |  ├─BufferedOutStream.cxx
|   |  ├─BufferedOutStream.h
|   |  ├─CMakeLists.txt
|   |  ├─Exception.cxx
|   |  ├─Exception.h
|   |  ├─FdInStream.cxx
|   |  ├─FdInStream.h
|   |  ├─FdOutStream.cxx
|   |  ├─FdOutStream.h
|   |  ├─FileInStream.cxx
|   |  ├─FileInStream.h
|   |  ├─HexInStream.cxx
|   |  ├─HexInStream.h
|   |  ├─HexOutStream.cxx
|   |  ├─HexOutStream.h
|   |  ├─InStream.h
|   |  ├─MemInStream.h
|   |  ├─MemOutStream.h
|   |  ├─OutStream.h
|   |  ├─RandomStream.cxx
|   |  ├─RandomStream.h
|   |  ├─TLSException.cxx
|   |  ├─TLSException.h
|   |  ├─TLSInStream.cxx
|   |  ├─TLSInStream.h
|   |  ├─TLSOutStream.cxx
|   |  ├─TLSOutStream.h
|   |  ├─ZlibInStream.cxx
|   |  ├─ZlibInStream.h
|   |  ├─ZlibOutStream.cxx
|   |  └ZlibOutStream.h
|   ├─os
|   | ├─CMakeLists.txt
|   | ├─Mutex.cxx
|   | ├─Mutex.h
|   | ├─os.cxx
|   | ├─os.h
|   | ├─Thread.cxx
|   | ├─Thread.h
|   | └winerrno.h
|   ├─network
|   |    ├─CMakeLists.txt
|   |    ├─Socket.cxx
|   |    ├─Socket.h
|   |    ├─TcpSocket.cxx
|   |    ├─TcpSocket.h
|   |    ├─UnixSocket.cxx
|   |    └UnixSocket.h
├─cmake
|   ├─cmake_uninstall.cmake.in
|   ├─StaticBuild.cmake
|   ├─TargetLinkDirectories.cmake
|   ├─Modules
|   |    ├─CMakeMacroLibtoolFile.cmake
|   |    ├─FindFfmpeg.cmake
|   |    ├─FindGmp.cmake
|   |    ├─FindIconv.cmake
|   |    ├─FindNettle.cmake
|   |    └FindPixman.cmake

```



