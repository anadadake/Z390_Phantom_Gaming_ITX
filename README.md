前言：


郑重感谢pcbeta的【beloved敏】的EFI分享。（http://bbs.pcbeta.com/viewthread-1839551-2-1.html）

如果有和本人相同硬件配置的人，EFI应该可以安装。

PS：本人有苹果笔记本电脑，安装黑苹果纯粹为好奇和测试。

黑苹果的基本信息：
系统和功能情况汇总：
系统 1：OSX Catalina 10.15.3

引导方式：Open Core

内置集成显卡：正常驱动

RX560独立显卡：正常驱动（仅使用了HDMI接口，DP未测试），HDMI接口的声音输出正常

wifi、蓝牙：正常使用

睡眠唤醒：正常使用

USB接口：正常使用

雷电3和Type-C：未测试

补充：使用了自己生产的序列号等三码。apple id正常登录，MAC App正常下载应用。隔空和随航为测试。

系统 2：Win 10

注意点1：网卡和蓝牙驱动使用了360驱动大师。在win10下网络速度一般，不如MAC下信号好。

注意点2：从苹果切换回win的时候，系统时间不一致，参考一下link的方法2，完美解决。https://cloud.tencent.com/developer/article/1562215


硬件配置：
CPU：Intel i5-9600K

主板：华擎科技 ASRock Z390 Phantom Gaming-ITX/ac

主板BIOS：4.40

显卡：华擎（ASRock）RX560 4G 幻影国度 钻石版

无线网卡（蓝牙）：BCM94360cs2+转卡

内存：美商海盗船(USCORSAIR)DDR4 3000 16GB * 2

NVMe硬盘 1（主板正面）：建兴(LITEON) 睿速系列 T10 240G M.2 NVMe固态硬盘 （安装win10）

NVMe硬盘 2（主板背面）：雷克沙 Lexar NM610 500G M.2 NVMe固态硬盘（安装OSX）

SATA固态硬盘：三星（SAMSUNG）500GB SSD固态硬盘 SATA3.0接口 860 EVO（windows的数据盘）

机箱： DAN A4-SFX v3 黑色

电源：海盗船金牌SF600 SFX电源 

CPU散热器：快睿纯铜C7（CPU风扇替换成了猫头鹰NF-A9x14 ）

机箱散热器：雅浚ProArtist Magisterial12 M12 散热风扇 

鼠标：罗技G304 无线鼠标

键盘：斐尔可 Filco 87 蓝牙双模茶轴侧刻版（FKBC87M/EFB2）

外置声卡：创新科技（Creative）Sound BlasterX G1 

补充：虽然测试过超频，CPU、内存和主板都不算雷，但是考虑到散热、噪音和双系统的稳定性，除内存使用XMP外，日常使用未超频。

主板的BIOS设置：
bios version：4.4.0

Advanced -> CPU Configuration

Software Guard Extensions(SGX):Enabled

CFG Lock: Disabled

Advanced -> Chipset Configuration

VT-d: disabled

IGPU Multi-Monitor:Enabled

Share Memory: 128M

Advanced -> Intel(R) Thunderbolt

Thunderbolt(R) Support -> Enabled

Thunderbolt(R) Boot Support -> Disabled

Thunderbolt Usb Support -> Enabled

Titan Ridge Workaround for OSUP -> Disabled

Security Level -> No Security

Sw SMI on TBT hot-plug -> Enabled

ACPI Notify on TBT Hot-plug -> Enabled

Advanced -> USB Configuration

Legacy USB Support -> Enabled

XHCI Hand-ff Enabled

Advanced -> Security Device Support -> Disabled

Security

Intel Platform Trust Technology -> Disabled

Secure Boot -> Disabled

Boot

Fast Boot -> Disabled

CSM -> Disabled

黑苹果安装说明：
电脑小白强烈劝退。

知识储备：

1. 会安装win10.对磁盘格式和分区有基础知识，如GPT、EFI等。

2. 会使用DiskGenius，会使用U盘的PE系统。

3. 熟悉电脑硬件，动手能力不弱。

4. 最好有白苹果的使用经验，没有的话，可以在虚拟机上玩玩苹果。

硬件准备：

1. 准备16G容量及以上的U盘并制作macOS 10.15.3安装镜像。下载地址：黑果小兵https://blog.daliansky.net/macOS-Catalina-10.15.3-19D76-Release-version-with-Clover-5103-original-image-Double-EFI-Version.html

2. 替换无线网卡:BCM94360cs2+转卡

3. 只安装一个需要安装MAC OS系统的NVME固态。（请注意备份数据，后续安装会格盘）

3. 主板BIOS安装上述BIOS设置并保存好。

软件准备：

windows环境：DiskGenius

MAC： Clover Configurator

本人提供的EFI：链接: https://pan.baidu.com/s/1l85rQVCHyDUkccZ-XxGGDA 提取码: 6ebm

核心安装步骤：

1. 替换U盘的启动EFI盘里面的EFI目录。（先删旧的，然后复制过去下载的EFI，保持目录结构）

2. 从u盘启动安装MAC。教程参考黑果小兵的教程。https://blog.daliansky.net/MacOS-installation-tutorial-XiaoMi-Pro-installation-process-records.html

3. 安装好之后，将硬盘的EFI启动分区的EFI目录删除，把U盘的EFI目录替换过去。

4. 更新本机的三码。（用Clover Configurator生成，并修改硬盘的EFI启动分区的EFI目录的配置文件。）

5. 如果有其他固态硬盘，可以安装回去。

6. 我是两块nvme固态，一个window10一个macOS catalina 10.15.4。 默认设置windows的NVME启动。如需切换MAC OS，启动的时候按F11键，选择mac即可。

