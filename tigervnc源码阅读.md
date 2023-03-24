# tigervnc源码阅读

## 目录结构

看一下tigervnc的源码目录（先只关注一级目录）

```
├─tigervnc
|  ├─BUILDING.txt
|  ├─CMakeLists.txt
|  ├─config.h.in
|  ├─LICENCE.TXT
|  ├─README.rst
|  ├─cmake
|  ├─common
|  ├─contrib
|  ├─doc
|  ├─java
|  ├─media
|  ├─po
|  ├─release
|  ├─tests
|  ├─unix
|  ├─vncviewer
|  ├─win
```

由于是在Linux（银河麒麟）系统上面，先看unix部分的

```
├─unix
|  ├─CMakeLists.txt
|  ├─xserver21.1.1.patch
|  ├─xserver116.patch
|  ├─xserver117.patch
|  ├─xserver118.patch
|  ├─xserver119.patch
|  ├─xserver120.patch
|  ├─common
|  ├─tx
|  ├─vncconfig
|  ├─vncpasswd
|  ├─vncserver
|  ├─x0vncserver
|  ├─xserver
```

## common

### RandrGlue.h

主要是声明一些获取状态的函数，具体实现在`x0vncserver`的`RandrGlue.c`中

`int vncGetScreenWidth(void);`

`int vncGetScreenHeight(void);`

`int vncRandRIsValidScreenSize(int width, int height);`

`int vncRandRResizeScreen(int width, int height);`

`void vncRandRUpdateSetTime(void);`

`int vncRandRHasOutputClones(void);`

`int vncRandRGetOutputCount(void);`

`int vncRandRGetAvailableOutputs(void);`

`char *vncRandRGetOutputName(int outputIdx);`

`int vncRandRIsOutputEnabled(int outputIdx);`

`int vncRandRIsOutputUsable(int outputIdx);`

`int vncRandRIsOutputConnected(int outputIdx);`

`int vncRandRCheckOutputMode(int outputIdx, int width, int height);`

`int vncRandRDisableOutput(int outputIdx);`

`int vncRandRReconfigureOutput(int outputIdx, int x, int y, int width, int height);`

`unsigned int vncRandRGetOutputId(int outputIdx);`

`int vncRandRGetOutputDimensions(int outputIdx, int *x, int *y, int *width, int *height);`

`int vncRandRCanCreateOutputs(int extraOutputs);`

`int vncRandRCreateOutputs(int extraOutputs);`



### unixcommon.h

声明变量`OutputIdMap`的类型

`typedef std::map<unsigned int, uint32_t> OutputIdMap;`

声明以下函数

`computeScreenLayout`

`setScreenLayout`

`tryScreenLayout`

`getPreferredScreenOutput`

仍然有几个函数未声明

不清楚原因的：`ResizeScreen`

内部函数，不做声明：`_setScreenLayout`





### randr.cxx

OutputIdMap 

std::map类型



rfb::Screen

id

dimensions

flags





output

screen

之间的关系？



#### ResizeScreen

`static int ResizeScreen(bool dryrun, int fb_width, int fb_height, std::set<unsigned int>* disabledOutputs)`

调整output的大小

**这个dryrun是个啥？**一个标识符用于区分set和try的两种情况？

会在两种情况下被间接调用

`setScreenLayout(int fb_width, int fb_height, const rfb::ScreenSet& layout, OutputIdMap *outputIdMap)`

`tryScreenLayout(int fb_width, int fb_height, const rfb::ScreenSet& layout, OutputIdMap *outputIdMap)`

分别对应

setScreenLayout

`_setScreenLayout(false, fb_width, fb_height, layout, outputIdMap)`

tryScreenLayout

`_setScreenLayout(true, fb_width, fb_height, layout, &dryrunIdMap)`



#### getPreferredScreenOutput

`int getPreferredScreenOutput(OutputIdMap *outputIdMap, const std::set<unsigned int>& disabledOutputs)`

感觉像是找到目前能用的output，然后返回在所有Output中的编号

`_setScreenLayout`中会被调用



firstDisabled、firstEnabled、firstConnected、firstUsable默认值均为-1

1.遍历所有的output

1.1.是否为已存在的output，是则跳过该次遍历

1.2.是否为Usable的output（vncRandRIsOutputUsable），是则跳过该次遍历

1.3.是否在disabledOutputs中已经存在，已经存在且firstDisabled为-1时，将firstDisabled置为i。

1.4.是否为Enabled的output（vncRandRIsOutputEnabled），Enabled且firstEnabled为-1时，将firstEnabled置为i。

1.5.是否为Connected的output（vncRandRIsOutputConnected），Connected且firstConnected为-1时，将firstConnected置为i。

1.6.firstUsable为-1时，firstUsable置为i。



2.状态判断以及给返回值（if-else if）

2.1.firstEnabled不为-1，优先返回firstEnabled

2.2.firstDisabled不为-1，再返回firstEnabled

2.3.firstConnected不为-1，再返回firstConnected

2.4.最后返回firstUsable



#### rfb::ScreenSet computeScreenLayout

`rfb::ScreenSet computeScreenLayout(OutputIdMap *outputIdMap)`

重新计算screenSet、outputIdMap 的状态？

存在output的变动时调用该函数？在outputIdMap中增加该output，同时在screenSet中分配一个screen。

1.遍历所有的output

1.1.output是否Enabled（vncRandRIsOutputEnabled），Enabled则跳过该次遍历

1.2.outputIdMap中已经存在的output，newIdMap直接拷贝outputIdMap。不存在则随机生成id，用outputId作为key，id作为value，添加到newIdMap中。

1.3.如果这个output没有screen，直接添加一个screen



2.newIdMap覆盖outputIdMap



3.如果screenSet中没有screen？那就add一个



#### _setScreenLayout

`static unsigned int _setScreenLayout(bool dryrun, int fb_width, int fb_height, const rfb::ScreenSet& layout, OutputIdMap *outputIdMap)`

1.clone mode 状态判断

不存在active的clone mode，继续运行



2.output数量判断：不够了就创建



3.调整screen的size



4.reconfigure所有的output（for遍历）

一堆状态检查......

4.1.是否为已存在的output，是则跳过该次遍历

4.2.找output对应的screen，不存在就干掉output

4.3.是否为Usable的output（vncRandRIsOutputUsable），返回rfb::resultInvalid

4.4.检查output是否支持该mode（是否支持这个宽高组合），不支持返回rfb::resultInvalid

4.5.output状态更改的打印

4.6.dryrun为真，则跳过该次遍历

4.7.重新配置output的mode和position



5.遍历screen，为新的screen分配output

5.1.遍历outputIdMap，screen是否已经存在对应的output，存在就跳过此次循环

5.2.调用getPreferredScreenOutput找一个没使用的output，找不到就returen rfb::resultInvalid。

5.3.将output作为key，ScreenSet的id作为value添加（或者覆盖）到outputIdMap中

5.4.是否为Usable的output（vncRandRIsOutputUsable），返回rfb::resultInvalid

5.5.检查output是否支持该mode（是否支持这个宽高组合），不支持返回rfb::resultInvalid

5.6.output状态更改的打印

5.7.dryrun为真，则跳过该次遍历

5.8.重新配置output的mode和position



6.遍历所有的output，关闭所有unused的outputs

6.1.是否为已存在的output，是则跳过该次遍历

6.2.output是否Enabled（vncRandRIsOutputEnabled），Enabled则跳过该次遍历

6.3.disable该output（vncRandRDisableOutput），并且释放资源



7.更新screen最后changed的时间戳



8.返回rfb::resultSuccess



#### setScreenLayout

`unsigned int setScreenLayout(int fb_width, int fb_height, const rfb::ScreenSet& layout, OutputIdMap *outputIdMap)`

调用

`return _setScreenLayout(false, fb_width, fb_height, layout, outputIdMap);`



#### tryScreenLayout

`unsigned int tryScreenLayout(int fb_width, int fb_height, const rfb::ScreenSet& layout, OutputIdMap *outputIdMap)`

相比`setScreenLayout`多了一行，相当于把`outputIdMap`的值拷贝到`dryrunIdMap`中

`OutputIdMap dryrunIdMap = *outputIdMap;`

调用，传入的`dryrunIdMap`，相当于不对原`outputIdMap`进行操作了

`return _setScreenLayout(true, fb_width, fb_height, layout, &dryrunIdMap);`



## tx

先不看，优先看x0vncserver和xserver

## vncconfig

先不看，优先看x0vncserver和xserver

## vncserver

先不看，优先看x0vncserver和xserver

## x0vncserver

### buildtime.c

就一行，一个记录build时间的数组？

`char buildtime[] = __DATE__ " " __TIME__;`



### Geometry.h

`Geometry`类构造函数没啥好说的

`Geometry(int fullWidth, int fullHeight);`



`recalc`：实际的创建操作

`void recalc(int fullWidth, int fullHeight);`



获取`rect`的对应信息

`int width() const { return m_rect.width(); }`

`int height() const { return m_rect.height(); }`

`int offsetLeft() const { return m_rect.tl.x; }`

`int offsetTop() const { return m_rect.tl.y; }`



`getRect`返回整个`rect`

`const rfb::Rect& getRect() const { return m_rect; }`



`parseString`：解析字符串，提取大小和坐标，最后返回裁剪后的`rect`并更改到`m_rect`

`rfb::Rect parseString(const char *arg) const;`



几个全局变量

`int m_fullWidth;`

`int m_fullHeight;`

`rfb::Rect m_rect;`

`static rfb::StringParameter m_geometryParam;`



### Geometry.cxx

#### m_geometryParam

`StringParameter Geometry::m_geometryParam`

用于控制显示给`vnc clients`的区域

`StringParameter`允许四个参数输入

`StringParameter(const char* name_, const char* desc_, const char* v, ConfigurationObject co=ConfGlobal);`

默认情况下后面两个参数都是空的，即默认全屏显示给`vnc clients`



#### Geometry

`Geometry::Geometry(int fullWidth, int fullHeight)`

构造函数，没啥好说的。按照传入的参数调用`recalc`函数，生成`rect`。



#### recalc

`void Geometry::recalc(int fullWidth, int fullHeight)`

1.按照传入的参数（`fullWidth`、`fullHeight`）初始化`m_rect`

2.按照`m_geometryParam`的解析后的数据（调用`parseString`函数解析），重新操作`m_rect`的范围。



#### parseString

`Rect Geometry::parseString(const char *arg) const`

一些字符串操作，不太想看



### Image.h

**`Image`类**

两种构造函数

`Image(Display *d);`

`Image(Display *d, int width, int height);`



析构函数为虚函数

`virtual ~Image();`



获取类名、获取类描述信息（均为虚函数）

`virtual const char *className() const{}`

`virtual const char *classDesc() const{}`



获取啥东西呢？也没返回值

`virtual void get(Window wnd, int x = 0, int y = 0);`

`virtual void get(Window wnd, int x, int y, int w, int h, int dst_x = 0, int dst_y = 0);`



注释写的：Copying pixels from one image to another.

将像素进行拷贝？











`virtual void updateRect(XImage *src, int dst_x = 0, int dst_y = 0);`

`virtual void updateRect(Image *src, int dst_x = 0, int dst_y = 0);`

`virtual void updateRect(XImage *src, int dst_x, int dst_y, int w, int h);`

`virtual void updateRect(Image *src, int dst_x, int dst_y, int w, int h);`

`virtual void updateRect(XImage *src, int dst_x, int dst_y, int src_x, int src_y, int w, int h);`

`virtual void updateRect(Image *src, int dst_x, int dst_y, int src_x, int src_y, int w, int h);`





**`ShmImage`类**



**`ImageFactory`类**





### Image.cxx





### PollingManager.cxx

### PollingManager.h

### PollingScheduler.cxx

### PollingScheduler.h

### qnum_to_xorgevdev.c

### qnum_to_xorgkbd.c

### RandrGlue.c

### TimeMillis.cxx

### TimeMillis.h

### x0vncserver.cxx

### XDesktop.cxx

### XDesktop.h

### XPixelBuffer.cxx

### XPixelBuffer.h



## xserver
