**科普翻译**系列文章精选外国英语技术博客、论文杂志以及有趣报道等进行翻译转述；本着学习知识，提升英语水平的初心，力求英语技术两不误。Go for it！

**原文地址**：https://zeptobars.com/en/read/open-microchip-asic-what-inside-II-msp430-pic-z80

## 第二部分：如何“打开”微芯片及其内部结构？

Part II: How to «open» microchip and what's inside? Z80, Multiclet, MSP430, PIC and more

第二部分：如何“打开”微芯片及其内部结构？ Z80，Multiclet，MSP430，PIC等

In this article we'll continue cracking microchips open. If you've missed first article - it's here.

这篇文章我们将继续探讨微型芯片的打开，如果你错过了第一篇文章，它在这里。

«Canonical» way of opening microchips:
Cut a small hole in the center of the chip with a dremel:

打开微芯片规范的方式：使用dremel（琢美，电磨机）在芯片中央切一个小孔。
![img](https://s.14.by/openchip1.jpg)

WARNING!: All operations with acids must be performed in a fume hood, with proper protection (gloves, gas mask, e.t.c).

警告！所有与酸有关的操作必须在通风口进行，并有适当的保护（手套，防毒面具等）

Put a droplet of fuming nitric or sulfuric acid there, heat up to ~100 ºC (~212 ºF). It is critical to use fuming acids - just concentrated (98% sulfuric or 70% nitric) won't cut it. After reaction ends - rinse with acetone, dry and put next droplet.

放一滴浓硝酸或者硫酸，加热到约100摄氏度（~212 ºF），使用浓酸是至关重要的，仅浓缩（98% 硫酸 或者 70%的硝酸）的酸是不会让它消减的。等反应结束后，使用丙酮冲洗，干燥后并放下一个滴液。


As a result we are getting exposed die, with all bond wires intact. The microchip still works - this might be useful if we want to probe it or modify eeprom data with UV laser.

我们将得到一个带完整焊线暴露的芯片的结果。这个微芯片仍然可以工作，如果我们想要去探索它或者使用UV激光修复eeprom数据，这可能很有用。
![img](http://s.14.by/openchip2.jpg)



### What's inside
里面是什么

K565RU5 (pin-compatible to 4164 DRAM chip) - 64 Kib DRAM chip, heart of most of amateur computers made in late soviet times and early 90's. There was also RU7 chip (256 Kib) but it was hard to buy.

K565RU5 (引脚兼容 4164 DRAM 芯片) - 64 kib 的动态随机存取存储器芯片，是苏联晚期90年代初，大多数企业计算机的心脏。这里也有RU7 芯片(256 kib),但是它很难买到。
![img](https://s.zeptobars.com/k565ru5.jpg)

Z80A - legendary successor of Intel 8080.
This is a photo of one of it's many clones. This one is likely made in DDR by MME company.
Die size - 4950x4720 µm, technology node - 5µm.

Z80A - Intel 8080 的传奇继任者
这是它许多复制品之一的一张图片。这可能是MME公司在DDR中制作的。
芯片尺寸-4950x4720 µm，技术节点5µm
![img](https://s.zeptobars.com/Z80A.jpg)

KR580VM80A just like KR580IK80A is an Intel 8080-compatible processor, which was in mass manufacturing in USSR until late 90's. Compared to KR580IK80A - die size is 20% smaller, IO peripherals are reworked.
Die size - 4634x4164 µm, 5µm technology.

KR580VM80A 就像KR580IK80A一样是兼容Intel 8080的处理器，它在苏联进行批量生产直到90年代后期。与KR580IK80A相比，芯片尺寸缩小了20%，IO外设也进行了重新设计。
芯片尺寸-4634x4164 µm，5µm技术。
![img](https://s.zeptobars.com/kr580vm80a.jpg)

MSP430F122 - 16-bit microcontroller made by Texas Instruments. What's interesting is that die is marked as MSP430F123, with larger flash size.

MSP430F122 - 是有TI(Texas Instruments/德州仪器)公司制造的16bit微控制器。有意思的是芯片标记为MSP430F123，具有更大的闪存。
![img](https://s.zeptobars.com/MSP430F122.jpg)


PIC12C508 - one of the "old" PIC's. Manufacturing technology - 1200nm, the oldest we've seen in microcontrollers being sold at the moment.
PIC12C508 - 老一代PIC（Programmable Interrupt Controller/可编程中断控制器）之一 。制造技术-1200nm，这是我们目前所见到的最古老的微控制器。
![img](https://s.zeptobars.com/PIC12C508.jpg)

PIC16C505 - another "old" PIC, again 1200nm.
PIC16C505 - 另一个的老一代PIC，同样是1200nm的制造技术。
![img](https://s.zeptobars.com/PIC16C505.jpg)

New RFID MIFARE chip from Moscow's metro - for several years Sitronics-Микрон was apparently using NXP RFID chips in Moscow's metro, but since February 2013 - we were finally able to find russian-made chips. New chip compared to NXP's one is 20% smaller, but not readable by NFC-readers in modern cell phones (might be a software issue). 180nm technology, aluminum metalization.

New RFID MIFARE chip from Moscow's metro -（莫斯科地铁的新型RFID MIFARE芯片）数年来，Sitronics-Микрон在莫斯科地铁中使用NXP RFID芯片，但自从2013年2月以来，我们终于能够找到俄罗斯制造的芯片。新型芯片相比于NXP要小20%，但不能够在现代手机的NFC读写器读取（可能存在软件问题）。180nm技术，铝金属化。
![img](https://s.zeptobars.com/mikron-mifare.jpg)


After metalization etch - it is clear that significant part of the chip is occupied by passive components (capacitors), and places under pads are empty.

在金属腐刻之后，很明显的，芯片的重要部分被无源元件（电容器）占据，焊盘下面的位置是空的。
![img](https://s.zeptobars.com/mikron-mifare-Si.jpg)


Dual timer 556 - one of the oldest chips still being manufactured.
Dual timer 556 - 仍然在生产的最古老的芯片之一。
![img](https://s.zeptobars.com/STM-NE556.jpg)


1886VE10 - Russian rad-hard 50Mhz microcontroller designed by Milandr and manufactured by Sitronics-Mikron on 180nm bulk-silicon technology. Radiation hardening is achieved by using edge-less transistors and 8T SRAM cells.
1886VE10 - 由Milandr设计并由Sitronics-Mikron用180nm体硅技术生产的俄罗斯抗辐射50Mhz微控制器。辐射硬化是通过使用无边缘晶体管和8T SRAM单元实现的。
![img](https://s.zeptobars.com/1886VE10.jpg)


After metalization etch:
金属蚀刻之后
![img](https://s.zeptobars.com/1886VE10-Si.jpg)

Not much to see in optical microscope:
在光学显微镜镜下看不到什么
![img](https://s.zeptobars.com/1886VE10-optical.jpg)

Much better via scanning electron microscope:
通过扫描电子显微镜要好的多
![img](https://s.zeptobars.com/1886VE10-SEM.jpg)

These bright cilinders - are tungsten via's left after metalization etch. This is an image from electron microprobing - sample is being bombarded by electron beam and X-Ray spectra is analyzed.
这些明亮的圆筒状物，是金属化蚀刻后剩下的钨通孔。这是来自电子微探测的图像-电子束轰击样品，并分析X射线光谱。
![img](https://s.zeptobars.com/edx.png)


STM32 STM32F103VGT6 - one of the largest STMicroelectronics microcontrollers on Cortex-M3 core. 1Mb of flash memory and 96kb of SRAM occupies it's enormous 5339x5188 µm die.

STM32 STM32F103VGT6 - Cortex-M3内核上最大的意法半导体微控制器之一。1Mb的闪存和96kb的SRAM占用了巨大的芯片尺寸（5339x5188 µm）
![img](https://s.zeptobars.com/STM32F103VGT6.jpg)

180nm SRAM is not really visible in optical microscope:
180nm SRAM 在光学显微镜下不能真正可见
![img](https://s.zeptobars.com/STM32F103VGT6-SRAM.jpg)

And again, electron microscope would help us:
同样，电子显微镜可以帮助我们
![img](https://s.zeptobars.com/STM32-SEM.jpg)


Multiclet MCp0411100101 - basically is a superscalar out-of-order processor(4-wide at the moment) designed in Russia. 100Mhz clock, 180nm manufacturing technology.
Die size - 10.2x10.2 мм.

After metalization etch: (Warning, high-resolution image might kill your browser)

Multiclet MCp0411100101 - 基本上是俄罗斯设计的超标量乱序处理器（目前4英寸），100Mhz时钟, 180nm 制造技术.芯片尺寸10.2x10.2mm
金属蚀刻后：
![img](https://s.zeptobars.com/multiclet-Si.jpg)


Area of SRAM cell- 21.28 µm2. Hence, each of 16 memory blocks has 72 Kibit of RAM. Obviously, ECC codes are used(72,64). Total accessible memory is 128 KiB.

Area of SRAM cell - 21.28 µm2（平方微米），16个存储块中的每个都有72Kib的RAM。显然，使用了ECC编码（72,64）。 可访问的总内存为128 KiB。
![img](https://s.zeptobars.com/multiclet-SRAM.jpg)

logo图案：
![img](https://s.zeptobars.com/multiclet-logo.jpg)
![img](https://s.zeptobars.com/multiclet-logo2.jpg)


Also, testing areas were cut along with the crystal, for example here is critical dimension test :
此外，测试区域也会随着晶体一起被切割，例如，这是关键尺寸测试：
![img](https://s.zeptobars.com/multiclet-reticle-cd-scribe-line.jpg)



------

**重要词汇：**

1. nitric: 硝酸盐，含氮的
2. sulfuric: 硫酸，含(六价)硫的
3. compatible: 兼容的，可共存的
4. soviet: 苏联的，苏联人
5. significant: 显著的，有重大意义的
6. crystal：结晶，晶体



------

内容|格子小七

图片|来源于网络

![img](http://wx4.sinaimg.cn/large/00709Ldkly1g0bglf55ovj30hu07w0tt.jpg)



