# 学习资料与使用顺序

## 你给的资料怎么用

| 资料 | 本月用法 | 阅读范围 |
|---|---|---|
| [RM 苍穹战队硬件组 Wiki](https://hw.rm.acgzjd.cn/training/) | 借用仿真先行、实操留证的节奏。它有自己的七周赛队安排 | A 段看[第 1 讲](https://hw.rm.acgzjd.cn/training/note1) 的元器件、PCB 工艺。D 段查[第 2 讲](https://hw.rm.acgzjd.cn/training/note2) 的实践方法及[第 4 讲](https://hw.rm.acgzjd.cn/training/note4) 的 STM32 最小系统 |
| [PCB 绘制指南重构版](https://github.com/BassttElSevic/the-guideline-of-how-to-draw-pcb/blob/main/PCB%E7%BB%98%E5%88%B6%E6%8C%87%E5%8D%97_%E9%87%8D%E6%9E%84%E7%89%88.md) | 跟着术语和从原理图到板厂文件的流程走，用小板练完一遍 | A 段看基本概念，D 段看第一块板的流程及迭代。指南推荐 C8T6 最小系统，本计划先用同一块 RC 板连通仿真与 PCB，另读 MCU 参考设计。工艺参数以板厂当前规则为准 |
| [SingularityZhang 的 Baka 模电笔记](https://blog.csdn.net/qq_41331935?type=blog) | 中文辅助。先认识 BJT/MOSFET/运放，再补结构和工作区 | [第 2 篇](https://blog.csdn.net/qq_41331935/article/details/156238852) 看常见器件，[第 3 篇](https://blog.csdn.net/qq_41331935/article/details/156279498) 看基本放大电路入口，[第 6 篇](https://blog.csdn.net/qq_41331935/article/details/156466150) 看运放组成导读。范围以索引和摘要为依据 |
| [Power_elec](https://github.com/Singularity-baakaka/Power_elec) | 学完线性电路、一阶动态后再进入开关电源。第 3 章的周期平均是进阶主题 | 第 1 章读占空比与储能器件。第 2 章读 MOSFET 的控制方式。第 3 章选读第 1–6 节，第 4 章选读 Buck。第 7 章的 TPS54302 典型应用和 Layout 留作后续工程参考 |

工作区的飞书导出《硬件组入门指南》补充了信息来源、数据手册、主动提问和 Markdown 记录的方法。本月范围以你贴出的 ConQU 学习要求为准。

## 主线资料

| 阶段 | 来源 | 找什么、怎么用 |
|---|---|---|
| A 微积分 | [MIT OCW 18.01SC](https://ocw.mit.edu/courses/18-01sc-single-variable-calculus-fall-2010/) | Unit 1 的极限、连续和导数定义，Unit 3 的定积分和微积分基本定理。每次读一个概念和一个例题，优先算电荷与电压变化 |
| A/B 电路表示和方程 | [MIT 6.01SC Circuits](https://ocw.mit.edu/courses/6-01sc-introduction-to-electrical-engineering-and-computer-science-i-spring-2011/pages/unit-3-circuits/circuits/) | Lecture 7 讲义及 Recitation 9、10，读 KCL/KVL、节点电压、回路电流。先读图，合上资料重列方程 |
| B 网络定理 | [All About Circuits · DC Network Analysis](https://www.allaboutcircuits.com/textbook/direct-current/chpt-10/) | 查 Mesh Current、Superposition、Thevenin、Norton。跟一道例题，再用同一个电路换参数验证 |
| C 动态 | [OpenStax RC §10.5](https://openstax.org/books/university-physics-volume-2/pages/10-5-rc-circuits) · [RL §14.4](https://openstax.org/books/university-physics-volume-2/pages/14-4-rl-circuits) | 看阶跃方程、初始条件、时间常数和曲线。先算 $\tau$，再用游标读数据 |
| C 交流 | [OpenStax 串联 RLC §15.3](https://openstax.org/books/university-physics-volume-2/pages/15-3-rlc-series-circuits-with-ac) | 看相量图、超前与滞后，再把 B 段的节点/网孔法改为复数方程 |
| A/D EDA | [嘉立创 EDA 专业版官方指南](https://prodocs.lceda.cn/cn/) · [嘉立创 PCB 工艺能力](https://jlcpcb.com/capabilities/Capab) | 编辑器教程查器件封装、原理图转 PCB、规则、铺铜、Gerber。按板层和铜厚查线宽/间距，再查孔径、环宽和板边要求。把实际选用的规则记入实验 |
| A/D MCU | [ST STM32F103C8 产品页](https://www.st.com/en/microcontrollers-microprocessors/stm32f103c8.html) | 查数据手册的电源、引脚与封装，区分 GPIO、ADC、定时器和调试。画功能框图时核对 VDD/VSS、VDDA/VSSA、NRST、BOOT、SWD 和时钟 |
| A 动力入门 | [Pololu 舵机控制接口](https://www.pololu.com/blog/17/servo-control-interface-in-detail) · [Microchip AN885](https://www.microchip.com/en-us/application-notes/an885) | 看常见 RC 舵机输入脉冲及内部位置环，阅读 AN885 的 BLDC 结构和换相。查具体型号的数据手册后再填真实参数 |
| D 后续电源参考 | [TI TPS54302 官方产品页](https://www.ti.com/product/TPS54302) | 只看典型应用和 Layout 建议，配合 Power_elec 第 7 章。记录反馈路径与高 di/dt 回路各在哪里 |

同一个问题的证据按用途选。公式看课程或教材，器件引脚和限值看对应型号手册，软件操作看同版本文档，制造约束看当前工艺页面。视频和博客适合找直观解释，记录时注明具体章节或时间点。

