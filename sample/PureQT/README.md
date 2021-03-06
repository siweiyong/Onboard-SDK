#DJI Onboard SDK QT Sample
##Intro
This example, which can run in both Windows and Linux platform, aims to help you understand and play with the basic flight procedures including:

* The Activation
* The Flight Control Obtainment
* The Flight control release
* The Take Off Procedure
* The Landing Procedure
* The Go Home Procedure
* The Attitude Control
* The Gimbal Control
* The Camera Control
* The Virtual RC Control
* The Waypoint Task Control
* The Hotpoint Task Control
* The Follow Me Task Control

Developers can play with this example via the GUI interaction interface of QT.


##Compile & Run Environment
The below environment are required.
* Qt Ver: QT 5.4 or later
* Compiler Ver: MinGW 4.9.2 or later; MSVC2012 or later


## Hardware Installation
* In order to communicate with the N1 Autopilot via the DJI OPEN protocal, a physical connection between your Onboard Device and the N1 Autopilot is required with a USB to TTL serial cable (SOLD Seperately).
* In order to monitor & control the flight, a remote controller connects to your Mobile Device (with the DJI GO APP running) is needed.

##Config and compile
1. Open *onboardSDK.pro* locates at *onboardSDK* sub-directory in *PureQT*.

2. Select a proper compiler and click *Configure Project* to proceed.

3. During the init process, enter the following info into the GUI interface including:

* APP ID
* Communication Key
* uart device name (e.g. COM1, COM2)
* baudrate

>Note: the 'baudrate' needs to be consistent with the setting in the DJI N1 PC assistant.

##Run
Click the green triangle icon on the bottom left corner to run the sample.
We recommend you first run this example in the simulator then carefully move to the real flight test.

##What You Can Expect
* You can see the flight control simulations on screen if you are using the DJI PC simulator. Otherwise, real flight happens.
* You can see the actual 'gimbal and camera' movement.
* You can see the image/video you capture from you Mobile Device.
* You can start a groundstation task.

ENJOY your flight!

##Additional hints

###install QT on manifold

* sudo apt-get update

* sudo apt-get install qtcreator

Now you have qt5.2.1 with out webkit package and serialport driver package

* sudo apt-get install libqt5webkit5

Now you only need a serialport driver

* sudo apt-get install libudev-dev

* git clone git://code.qt.io/qt/qtserialport.git

* cd qtserialport

* git checkout origin/old/5.2

* cd ..

* mkdir qtserialport-build

* cd qtserialport-build

* qmake ../qtserialport/qtserialport.pro

* make

* sudo make install

Now you have a serialport driver in version 5.2, it still could not run the PureQT example.

Continue and build the 5.3 version's source code.

* cd ../qtserialport/

* git checkout origin/5.3

* cd ../qtserialport-build/

* make

In this step the compile would fail, ignore it and continue finishing the following steps

* sudo make install

* make

At this time, the build will success.

* sudo make install

Now you could use PureQT example

* sudo qtcreator

Default serialport name is ttyTHS1

#DJI Onboard SDK QT例程

##简介

QT 例程是我们基于 QT 平台实现的 SDK 例程，它可以运行在 Windows 或者 Linux 平台上并可以完成如下命令：

* 激活
* 获取控制权
* 释放控制权
* 起飞
* 降落
* 自动返航
* 姿态控制
* 云台控制
* 相机控制
* 虚拟遥控
* 航点指令
* 热点环绕指令
* 智能跟随指令

开发者可以通过程序的图形界面来进行交互和测试。

##调试与运行环境
我们成功测试了如下运行环境：
* QT 版本： QT 5.4 或更新。
* 编译器版本： MinGW 4.9.2 或更新；MSVC2012或更新。

##硬件安装

* 为了能够与 M100 的 N1 主控进行通信，开发者需要自行购买 USB 转 TTL 的串口转接模块。

* 为了更好的监控飞机状态，我们建议开发者在调试的时候运行 DJI GO 来实时查看飞机当前状态信息。

##配置和编译

1. 打开 `onboardSDK` 中`PureQT` 目录下的 `onboardSDK.pro` 载入 QT 例程。
2. 选择合适的编译器并编译项目。
3. 在程序中选择好正确的设备和波特率，以及配置好激活所需的 APP ID 与 key

##运行

在 QT 中点击绿色三角来运行程序，你可以在模拟器中对其进行测试。

##特别提示

###在manifold内安装QT

* sudo apt-get update

* sudo apt-get install qtcreator

至此，已经安装了qt5.2.1，但是缺少webkit和串口驱动

* sudo apt-get install libqt5webkit5

至此就只剩下串口驱动了

* sudo apt-get install libudev-dev

* git clone git://code.qt.io/qt/qtserialport.git

* cd qtserialport

* git checkout origin/old/5.2

* cd ..

* mkdir qtserialport-build

* cd qtserialport-build

* qmake ../qtserialport/qtserialport.pro

* make

* sudo make install

现在有了5.2版本的串口驱动，但是这个驱动是不能正常使用的

* cd ../qtserialport/

* git checkout origin/5.3

* cd ../qtserialport-build/

* make

这次make会失败，不要理他，继续执行下面的步骤

* sudo make install

* make

这次make会成功

* sudo make install

完成安装。用sudo权限开启qtcreator。

* sudo qtcreator

默认串口名称为ttyTHS1
