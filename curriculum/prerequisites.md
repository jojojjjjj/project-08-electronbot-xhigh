# 前置知识 | Prerequisites

> **重要提示 | Important Note：** 本项目是系列课程中的**进阶项目**，前置知识要求远高于其他项目。如果你刚完成 Project 05（ESP-SparkBot）或类似入门项目，你已具备部分基础，但仍需额外补充STM32和焊接相关知识。如果你是零基础，强烈建议先完成一个入门级嵌入式项目。
>
> This is an **advanced project** in the series with significantly higher prerequisites than other projects. If you have completed Project 05 (ESP-SparkBot) or a similar entry-level project, you have some of the foundations but will still need to study STM32 and soldering specifically. If you are a complete beginner, it is strongly recommended to complete an introductory embedded project first.

## 必备基础 | Required Knowledge

### 1. C语言中级水平
在开始本项目前，你应该**熟练掌握**以下C语言知识：

Before starting, you should be **proficient** with the following C language topics:

| 知识点 | 要求程度 | 说明 |
|--------|----------|------|
| 变量与数据类型 | 熟练 | uint8_t, uint16_t, uint32_t, int32_t, size_t 等嵌入式常用类型 |
| 指针与地址 | 熟练 | 指针算术、函数指针、指向结构体的指针、二级指针 |
| 结构体与枚举 | 熟练 | struct, enum, typedef, 位域(bit-field) |
| 回调函数 | 掌握 | 函数指针作为参数、HAL库回调模式 |
| 位操作 | 熟练 | &, \|, ^, ~, <<, >>（用于标志位判断、掩码等，本项目主线用 HAL，不要求手写寄存器级代码） |
| volatile关键字 | 理解 | 为什么中断和硬件寄存器需要volatile |
| 预处理器 | 了解 | #define, #ifdef, 宏函数, 条件编译 |
| 链接脚本基础 | 了解 | .ld文件的作用、内存分区(FLASH/SRAM)概念 |
| 内存管理 | 理解 | 栈 vs 堆、静态变量、数组越界危害 |

**推荐学习资源：**
- [C语言菜鸟教程](https://www.runoob.com/cprogramming/c-tutorial.html) -- 中文基础教程
- [C语言中文网](http://c.biancheng.net/c/) -- 系统学习C语言
- B站搜索 "C语言进阶" -- 重点看指针、结构体、位操作相关视频
- *《C Primer Plus》* 第6版 -- 经典参考书，重点阅读第12-16章

### 2. 基础电路与PCB知识
本项目需要焊接贴片IC和QFN封装，电路知识要求远高于入门项目：

This project requires soldering SMD ICs and QFN packages -- circuit knowledge requirements are significantly higher than entry-level projects:

| 知识点 | 要求程度 | 说明 |
|--------|----------|------|
| 电压/电流/电阻 | 熟练 | 欧姆定律、功率计算、分压分流 |
| 原理图阅读 | 基本掌握 | 能看懂MCU最小系统、电源电路、外设连接 |
| 万用表使用 | 熟练 | 测电压、测通断、测电阻、排查短路 |
| 示波器基础 | 了解 | 能看波形、测频率、判断信号质量 |
| 贴片元件认知 | 了解 | 0402/0603/0805封装尺寸、QFN/LQFP封装识别 |
| PCB基本概念 | 了解 | 走线、过孔、丝印、焊盘、铜箔 |

**推荐学习资源：**
- B站搜索 "手工焊接贴片IC教程" -- 学习QFN焊接技巧
- [立创EDA教程](https://lceda.cn/) -- 在线PCB设计工具和教程
- B站搜索 "示波器入门教程" -- 了解基本操作

### 3. Python基础
用于Unity脚本理解和SDK工具使用：

For Unity scripting and SDK tool usage:

| 知识点 | 要求程度 | 说明 |
|--------|----------|------|
| 变量和数据类型 | 熟练 | str, int, float, list, dict |
| 函数定义与调用 | 熟练 | 参数、返回值、默认参数 |
| 类与对象 | 基本了解 | class定义、__init__、方法调用 |
| 文件操作 | 了解 | 读写文件、JSON处理 |
| pip包管理 | 了解 | 安装第三方库（opencv-python, requests等） |

### 4. 线性代数基础
用于理解旋转矩阵和6自由度运动学计算：

For understanding rotation matrices and 6-DOF forward kinematics:

| 知识点 | 要求程度 | 说明 |
|--------|----------|------|
| 矩阵乘法 | 基本了解 | 2x2和3x3矩阵乘法 |
| 坐标变换 | 基本了解 | 二维/三维坐标系旋转 |
| 三角函数 | 熟练 | sin, cos, atan2在运动学中的应用 |
| 向量 | 了解 | 向量表示、向量运算 |

**推荐学习资源：**
- B站搜索 "3Blue1Brown 线性代数的本质" -- 直观理解矩阵和变换
- 高中数学教材三角函数章节 -- 复习sin/cos基本公式

### 5. 基本英语能力
本项目涉及大量英文技术文档阅读，对英语能力要求较高：

This project involves extensive English technical document reading:

| 能力 | 要求程度 | 说明 |
|------|----------|------|
| 技术文档阅读 | 基本掌握 | 能借助翻译工具阅读STM32 Reference Manual |
| Datasheet阅读 | 基本了解 | 能找到引脚定义、电气特性、时序参数 |
| 错误信息阅读 | 熟练 | 能理解编译器错误和运行时错误 |
| 英文搜索 | 熟练 | 能用英文关键词在Google/StackOverflow搜索问题 |

> **提示 | Tip：** 不要求英语很好，但需要习惯借助翻译工具（DeepL、Google Translate）阅读技术文档。STM32的官方文档是英文的，这是无法回避的。

## 加分项 | Nice-to-Have (Not Required)

以下知识不是必需的，但有基础会显著提高学习效率：

The following are not required but will significantly improve your learning efficiency:

| 知识 | 加分点 |
|------|--------|
| Arduino/STM32开发经验 | 有过MCU编程经验，Day 1-5会更轻松 |
| Unity/C#基础 | 有Unity使用经验，Day 9-11进度更快 |
| 手工焊接经验 | 有贴片焊接经验（0603及以上），Day 3会顺利很多 |
| 3D打印经验 | 了解切片软件和打印参数调整 |
| Git版本管理 | 能够使用Git管理代码 |
| OpenCV/计算机视觉基础 | 了解图像处理基本概念 |
| ROS/机器人学基础 | 理解坐标系变换和运动学 |

## 硬件要求 | Hardware Requirements

### 必备设备
- **笔记本电脑**：Windows 10/11（**必须**，STM32CubeIDE和Unity在Windows上体验最佳）
- **USB 3.0接口**：用于连接USB摄像头和高带宽数据传输
- **ST-Link V2调试器**：用于STM32固件烧录和在线调试（课程提供）
- **USB Type-C数据线**：用于连接ElectronBot主板

### 推荐设备
- **外接显示器**：强烈推荐，便于一边看教程一边编码
- **USB转串口模块**：CP2102或CH340（备用调试工具）
- **放大镜/台灯**：辅助贴片焊接时查看焊点

### 课程提供
- ElectronBot套件（包含PCB + 所有元器件 + 3D打印外壳 + 舵机 + 屏幕）
- 焊接工具（温控电烙铁、焊锡、助焊剂、镊子、吸锡器、热风枪等）
- 万用表
- ST-Link V2调试器
- USB摄像头模块

## 自学检查清单 | Self-Study Checklist

在Day 1之前，请尝试完成以下练习。如果你能独立完成大部分，说明你已经准备好了：

Before Day 1, try these exercises. If you can complete most of them independently, you are ready:

### 检查1：C语言中级与 HAL 抽象理解
```c
// 请理解以下代码，体会 HAL 库是如何把"操作硬件"变得好读的
#include "stm32f4xx_hal.h"   // STM32 HAL 库头文件

// 声明一个 LED 对应的 GPIO 引脚和端口（HAL 用结构体描述，不直接碰地址）
GPIO_TypeDef *LED_PORT = GPIOA;
uint16_t LED_PIN = GPIO_PIN_5;   // PA5

// HAL 库提供的封装函数：点亮 / 熄灭 / 翻转一个引脚
void led_on(void) {
    HAL_GPIO_WritePin(LED_PORT, LED_PIN, GPIO_PIN_SET);     // 输出高电平
}

void led_off(void) {
    HAL_GPIO_WritePin(LED_PORT, LED_PIN, GPIO_PIN_RESET);   // 输出低电平
}

void led_toggle(void) {
    HAL_GPIO_TogglePin(LED_PORT, LED_PIN);                  // 翻转电平
}

// 回调函数示例（HAL 库大量使用回调，比如接收完一组数据后通知你）
typedef void (*EventCallback)(int event_type);

void register_callback(EventCallback cb) {
    // 在中断中调用: cb(EVENT_BUTTON_PRESS);
}

// 问题：
// 1. HAL_GPIO_WritePin 为什么要传"端口 + 引脚"两个参数，而不是直接写一个地址？
//    （提示：想想"建筑图纸 vs 直接砌墙"——HAL 给你的是图纸上的符号，不是砖头的坐标。）
// 2. 如果不用 HAL，直接操作硬件需要做什么？为什么 HAL 这一层让代码更好读、更好移植？
// 3. EventCallback 是什么类型？在中断里调用 cb(...) 和在主循环里调用有什么不同？
```

> **为什么这样学 | Why learn it this way:**
> 早期嵌入式开发要直接往芯片寄存器地址（一串十六进制数字）里写值来控制引脚，既难读也容易写错，换个芯片就得全改。HAL（Hardware Abstraction Layer，硬件抽象层）把这些细节包成 `HAL_GPIO_WritePin(...)` 这样的函数——你只说"点亮 PA5"，不用管 PA5 在芯片里对应哪个地址、哪一位。本项目主线全程用 HAL，所以前置检查也只要求理解 HAL 的思路，不要求背寄存器地址。位操作（`& | ~ <<`）作为 C 语言基础知识仍然要会（见上面 C 语言知识点表），但不需要会手写寄存器级代码。

### 检查2：结构体与 HAL 的配置思路
```c
// 请理解以下代码，这是 STM32 HAL 库里"用一个结构体描述外设配置"的常见模式
#include "stm32f4xx_hal.h"

// HAL 用一个结构体把 GPIO 的所有配置项打包在一起
GPIO_InitTypeDef gpio_init = {0};

gpio_init.Pin   = GPIO_PIN_5;          // 哪个引脚：PA5
gpio_init.Mode  = GPIO_MODE_OUTPUT_PP; // 模式：推挽输出（能输出高低电平）
gpio_init.Pull  = GPIO_NOPULL;         // 上下拉：不接
gpio_init.Speed = GPIO_SPEED_FREQ_LOW; // 速度：低速足够（点 LED 不需要快）

// 一行调用就把上面的配置应用到硬件
HAL_GPIO_Init(GPIOA, &gpio_init);

// 问题：
// 1. 为什么 HAL 用一个结构体（GPIO_InitTypeDef）来描述配置，而不是写一长串函数参数
//    或者直接往寄存器里写数字？（提示：结构体像一张"配置表"，字段清楚、好读好改。）
// 2. 如果想让 PA5 同时换一个功能（比如改成输入），你需要改结构体的哪个字段？为什么这样改比
//    直接改硬件寄存器更省心？
// 3. HAL_GPIO_Init(GPIOA, &gpio_init) 里的 & 是什么意思？为什么传指针而不是传整个结构体？
```

> **为什么这样学 | Why learn it this way:**
> HAL 库内部其实也会用结构体、位域、union 这些 C 技巧去对应硬件寄存器的位，但那是库作者的事——你作为使用者，只需要会"填一张配置表（结构体），然后调用 `HAL_GPIO_Init` 让它生效"。这个模式在配置串口、I2C、SPI、USB 时会反复出现，所以前置检查只要求理解"结构体当配置表用"这个思路。位域和 union 作为 C 语言知识点了解即可（遇到库源码能看懂大概），不需要自己手写去对齐寄存器位。

### 检查3：运动学基础概念
```
请回答以下问题（不要求精确计算，理解概念即可）：

1. 一个舵机安装在关节处，旋转角度为0-180度。如果舵机臂长5cm，
   末端在0度和90度时的位置分别是多少？（假设原点在舵机轴心）

2. 三个舵机串联组成一个简单的机械臂：
   - 舵机1：底座旋转（0-180度）
   - 舵机2：大臂俯仰（0-180度）
   - 舵机3：小臂俯仰（0-180度）
   如果大臂长10cm，小臂长8cm，请描述"正运动学"要解决什么问题。

3. sin(30度) = ?  cos(60度) = ?  atan2(1, 1) = ?

提示：
1. (5, 0) 和 (0, 5) -- 用三角函数计算
2. 正运动学：已知各关节角度，求末端执行器在空间中的位置
3. 0.5, 0.5, 45度
```

### 检查4：STM32概念预习
```
请在开始课程前了解以下概念（不需要深入理解，知道是什么即可）：

1. ARM Cortex-M4是什么？和Arduino的AVR芯片有什么区别？
2. 什么是HAL（Hardware Abstraction Layer）？为什么要用HAL库？
3. STM32的时钟树是什么？为什么MCU需要配置时钟？
4. 什么是中断（Interrupt）？什么是NVIC？
5. DMA是什么？为什么DMA可以提高系统效率？

推荐资源：
- B站搜索 "STM32入门教程" -- 看前3集了解基本概念
- STM32CubeIDE官方介绍页面 -- 了解IDE功能
```

### 检查5：命令行与环境
```bash
# 请在命令行中完成以下操作，确保你的环境基本可用
# Windows (PowerShell):

# 1. 检查Python是否已安装
python --version

# 2. 检查Git是否已安装
git --version

# 3. 创建项目目录
mkdir electronbot-workspace
cd electronbot-workspace

# 4. 创建一个简单的Python脚本并运行
echo 'print("Hello, ElectronBot!")' > test.py
python test.py

# 5. 检查是否有可用的USB端口
# （连接一个USB设备后）
lsusb  # Linux
# 或在设备管理器中查看 "端口(COM和LPT)"  # Windows
```

## 如果你还没有准备好 | If You're Not Ready Yet

本项目前置知识量较大，以下是分阶段的补课建议：

This project has significant prerequisites. Here are staged catch-up recommendations:

1. **C语言不够扎实**：花3-5天集中补强指针、结构体、位操作。重点练习位操作（嵌入式开发最常用）
2. **无焊接经验**：花1-2天练习。建议购买一套贴片焊接练习板（0805封装开始），先练通孔元件再练贴片
3. **无STM32基础**：花2-3天看STM32入门教程（B站），了解CubeIDE基本操作和HAL库概念
4. **电路知识薄弱**：花1-2天复习基本电路知识，重点学会读原理图
5. **Python不熟练**：花1天快速过一遍Python基础语法

## 推荐预习 | Recommended Pre-reading

在开始课程之前，建议先浏览以下资料（不要求全部理解，建立初步印象即可）：

### 必读（高优先级）
- **ElectronBot开源项目**：[github.com/xcongyufa/ElectronBot](https://github.com/xcongyufa/ElectronBot) -- 浏览README和项目架构
- **STM32F4 Datasheet**：浏览第1-3章，了解芯片特性、引脚定义、内存映射
- **STM32CubeIDE快速入门**：搜索 "STM32CubeIDE Getting Started" -- 了解IDE基本操作

### 推荐（中优先级）
- **ARM Cortex-M4技术参考手册摘要**：搜索 "Cortex-M4 Technical Reference Manual" -- 了解内核特性
- **GC9A01屏幕驱动芯片Datasheet**：搜索 "GC9A01 datasheet" -- 了解SPI屏幕驱动原理
- **PID控制入门**：B站搜索 "PID控制最通俗讲解" -- 直观理解PID控制

### 可选（低优先级）
- **Unity基础教程**：搜索 "Unity入门教程" -- 了解Unity界面和C#脚本基础
- **OpenCV Python入门**：搜索 "OpenCV Python tutorial" -- 了解基本图像处理
- **I2C协议介绍**：搜索 "I2C总线协议详解" -- 理解I2C通信原理

## 学习时间估算 | Time Estimate

| 学员水平 | 前置知识准备时间 | 说明 |
|----------|-----------------|------|
| 有STM32开发经验 + 焊接经验 | 0-4小时（浏览即可） | 重点看ElectronBot项目架构 |
| 有ESP32/Arduino经验 + 简单焊接 | 2-4天 | 需要学习STM32 HAL库和贴片焊接 |
| 有C语言基础 + 简单电路知识 | 5-7天 | 需要补STM32、焊接、电路 |
| 有编程基础但无嵌入式经验 | 1-2周 | 建议先完成一个入门级嵌入式项目 |
| 完全零基础 | 3-4周 | **强烈建议先完成 Project 05 或类似入门项目** |

## 软件安装清单 | Software Installation Checklist

在课程开始前，请确保以下软件已安装：

Before the course begins, please ensure the following software is installed:

| 软件 Software | 版本 Version | 下载地址 Download | 用途 Purpose |
|--------------|-------------|------------------|-------------|
| STM32CubeIDE | 最新版 Latest | [st.com/stm32cubeide](https://www.st.com/en/development-tools/stm32cubeide.html) | STM32开发IDE |
| Unity Hub | 最新版 Latest | [unity.com/download](https://unity.com/download) | Unity项目管理 |
| Unity Editor | 2021.3 LTS | 通过Unity Hub安装 | 桌面应用开发 |
| VSCode | 最新版 Latest | [code.visualstudio.com](https://code.visualstudio.com/) | 通用代码编辑器 |
| Python | 3.9+ | [python.org](https://www.python.org/downloads/) | SDK工具和脚本 |
| Git | 最新版 Latest | [git-scm.com](https://git-scm.com/downloads) | 版本管理 |
| ST-Link驱动 | 最新版 Latest | [st.com/st-link-driver](https://www.st.com/en/development-tools/stsw-link009.html) | ST-Link调试器驱动 |
| 串口调试助手 | 任意 | 如 SSCOM、PuTTY | 调试输出查看 |

### 安装步骤 Installation Steps

1. **安装STM32CubeIDE**：从ST官网下载并安装，安装时会自动包含STM32CubeMX和必要的工具链
2. **安装Unity Hub**：下载并安装Unity Hub，通过Hub安装Unity 2021.3 LTS编辑器
3. **安装Python**：下载并安装Python 3.9+，安装时**必须**勾选 "Add Python to PATH"
4. **安装VSCode**：下载并安装Visual Studio Code，推荐安装C/C++和C#扩展
5. **安装Git**：下载并安装Git，使用默认设置即可
6. **安装ST-Link驱动**：下载并安装STSW-LINK009驱动程序
7. **验证安装**：
   - 打开STM32CubeIDE，确认能创建新工程
   - 打开Unity Hub，确认能创建新项目
   - 打开命令行，输入 `python --version` 和 `git --version` 确认可用

> **提示 | Tip：** STM32CubeIDE安装包较大（约1GB），请提前下载。Unity Editor下载也较慢，建议提前一晚安装。如果网络不好，可以使用离线安装包。

*最后更新：2026-05-27*
