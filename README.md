# KasperDev-Architecture
编玩编学Kasper创作的GPU架构概念  | GPU architecture concept created by KasperDev
### 这啥呀？ | What's this?
KasperDev-Architecture 是由编玩编学Kasper创作的一种芯片系统架构，采用三维垂直堆叠+侧边独立功能模组的方式，将计算、缓存、存储、IO、供电、与光互连在空间上几乎彻底解耦。
KasperDev-Architecture is a chip system architecture created by Kasper from KasperDev. It adopts three-dimensional vertical stacking combined with side-mounted independent functional modules to achieve nearly complete spatial decoupling of computing,caching, storage, I/O, power supply, and optical interconnection.
### 所以它是啥样的？ | Core Idea
计算核心在四角，缓存在中心，供电在东，光IO在北。为什么分别是东和北？https://www.bilibili.com/video/BV1sYQmY7EoM/
The compute cores are situated at the four corners, the cache resides in the center, power delivery is on the east, and optical I/O is on the north—a layout that physically separates the noisy power delivery circuits from the sensitive optical receivers, minimizing electromagnetic coupling.
顶层：四角计算核心（含中心L1/L2私有缓存）。算力主体，热源置顶，紧贴散热器。
Top Layer: Compute cores at the four corners and private L1/L2 caches in the center constitute the primary compute fabric. Thermal sources are positioned at the apex to ensure direct contact with the heatsink.
中层：中央L3共享缓存+四角TSV垂直通道。全芯片共享缓存，数据枢纽，垂直互联。
Middle Layer: Central L3 shared cache and TSV vertical channels at the four corners. This layer serves as the chip-wide shared memory pool, the data hub, and the vertical interconnect fabric.
底层：中央大大大大大大大大大大（其实也没那么大）容量SRAM+中控+四角IO外设。全局控制、大大大大大大大大大大容量存储、对外通信。
Bottom Layer: Central massive-massive-massive SRAM pool — well, it's not *that* huge — the brain (control), and I/O peripherals in the corners. The gig: global orchestration, a huuuuuge chunk of memory, and off-chip chatter.
东侧：垂直供电模组。独立供电，全链路低噪音供电。
East edge: Vertical power module. Isolated power, super clean rails end-to-end.
北侧：硅光IO引擎（外置光源）。拿他用来芯片间超高速光互连。
North edge: Silicon photonics engine—light source is off-chip. That's what we use for the screaming-fast optical links between dies.
### 概念草图 | Concept Sketch
见“图1.png”“图2.png”。
See below for "图1.png" and "图2.png".
2026年4月7日深夜于iPad Procreate绘画。
Drawn late night, April 7, 2026, on iPad using Procreate.
