---
title: RAM ROM Flash UFS 区别
date: 2021-04-04 19:06:11
updated: 2021-04-04 19:06:11
categories:
tags:
- [RAM]
- [ROM]
- [Flash]
- [eMMC]
- [UFS]
---

# 1.RAM分类

|              |                    |             |                                                              |
| ------------ | ------------------ | ----------- | ------------------------------------------------------------ |
| RAM          | DRAM               | SDRAM       | 同步动态随机存取存储器，需要刷新，速度快，容量大             |
| 掉电丢失数据 | 动态随机存取存储器 | DDR SDRAM   | 双倍速率SDRAM（内存条），工作电压2.5V/2.6V                   |
|              |                    | DDR2 SDRAM  | 内存时钟 200~533MHz，工作电压1.8V                            |
|              |                    | DDR3 SDRAM  | 内存时钟 400~1066MHz，工作电压1.5V/1.35                      |
|              |                    | DDR4 SDRAM  | 16bit预取机制（DDR3为8bit），工作电压1.2V                    |
|              |                    | DDR5 SDRAM  | 工作电压1.1V                                                 |
|              |                    | GDDR SDRA   | 图形DDR，目前有GDDR2~6                                       |
|              |                    | LPDDR SDRAM | 低功率DDR,时钟166MHz，LPDDR2其工作电压1.2V，时钟100~533MHz   |
|              |                    | RDRAM       |                                                              |
|              | SRAM               |             | 静态随机存取存储器，不用刷新，速度可以非常快，价格高，容量小，一种置于CPU的高速缓存（Cache) |
|              | DARAM              |             | 双口RAM，一个时钟周期可访问两次                              |
|              | SARAM              |             | 单口RAM，一个时钟周期访问一次                                |
|              | PSRAM              |             | 伪静态存储器，内部自带刷新机制                               |

# 2.ROM分类

|      |         |                                                  |
| ---- | ------- | ------------------------------------------------ |
| ROM  | ROM     | 只能写入一次，如CD-ROM、DVD-ROM                  |
|      | PROM    | 可编程ROM，内部是行列式熔断丝                    |
|      | EPROM   | 紫外线可擦除，写入时需要用编程器产生高压脉冲信号 |
|      | OTP-ROM | 一次可编程ROM，写入原理与EPROM相同               |
|      | EEPROM  | 电可擦除                                         |

# 3.Flash分类

|       |            |                                                              |                    |
| ----- | ---------- | ------------------------------------------------------------ | ------------------ |
| Flash | NOR Flash  | 以扇区为单位写，可随机读取，程序可直接运行，容量小           | Parallel NOR Flash |
| 闪存  |            |                                                              | Serial NOR Flash   |
|       | Nand Flash | 以块为单位读写，不能直接运行程序，容量大                     | SLC、MLC、TLC、QLC |
|       | MMC        | MMC接口、NAND Flash、主控制器                                |                    |
|       | eMMC Flash | 嵌入式存储解决方案，带有MMC接口（并行数据总线）、NAND Flash、主控制器 |                    |
|       | UFS        | 串行数据总线、Nand Flash、主控制器                           |                    |

> eMMC的最新 5.1标准理论最高值最高可以达到400MB/s，UFS的最大优势就是双通道双向读写，UFS3.0接口带宽最高23.2Gbps，也就是2.9GB/s。

> eMMC的电路接口与SD卡是一样的，SD卡只是焊接在PCB上，然后做上金手指和外壳。eMMC支持8位和4位数据总线，SD卡标准是4位数据总线。

> eMMC有两条总线，分别传输指令数据输入和输出，而且因为是并行总线还要有额外的data strobe。而UFS则是有两条差分的数据lane，指令和数据都是以packet的形式发送的。

> SSD = 主控 + DRAM缓存 + Nand Flash

> eMMC = 主控 + Nand Flash + 标准封装接口