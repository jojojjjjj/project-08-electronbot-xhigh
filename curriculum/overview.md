# 课程总览 | Curriculum Overview

## 项目名称 | Project Name
ElectronBot 进阶桌宠机器人 | ElectronBot Advanced Desktop Pet

## 项目定位 | Project Positioning
本项目是一个面向有一定嵌入式基础的**高中进阶暑期硬件实践课程**，为期12天（约2周半），每天6-8小时。学员将从零开始，使用STM32F4芯片（ARM Cortex-M4）开发一个具备6自由度舵机控制、环形屏幕表情、手势/IMU 触发动作的桌面宠物机器人。

> **夏令营 MVP 范围 | Camp MVP Scope：** 12 天时间紧，我们把交付目标收窄为**屏幕表情 + 手势/IMU 触发动作**这一核心体验（详见 `assignments.md` 的 MVP 定义）。视觉跟随（OpenCV 人脸检测）、Python 上位机为 Day 9-10 内容；OpenCV 姿态估计、3D 虚拟形象同步、LLM 对话与语音流水线均为 **stretch 选做**，学有余力的同学挑战，不影响 MVP 评分。原 ElectronBot 用 Unity+C#+C++ DLL 上位机，夏令营为压薄语言栈改用 **Python 上位机**直接走 USB 桥接。

This is an **advanced summer hardware practicum** for high school students with some embedded systems background, spanning 12 days (approx. 2.5 weeks) at 6-8 hours per day. Students build a desktop pet robot from scratch using the STM32F4 (ARM Cortex-M4) chip, featuring 6-DOF servo control, round-screen facial expressions, and gesture/IMU-triggered actions.

> **Camp MVP scope:** With only 12 days, we narrow the deliverable to the core experience of **screen expressions + gesture/IMU-triggered actions** (see the MVP definition in `assignments.md`). OpenCV face detection and the Python host app are Day 9-10 content; OpenCV pose estimation, 3D avatar sync, LLM dialogue, and the voice pipeline are all **stretch goals** for students who finish the MVP. The original ElectronBot uses a Unity+C#+C++ DLL host app; the camp swaps this for a **Python host app** over USB to keep the language stack thin.

## 学习目标 | Learning Objectives

### 知识目标 | Knowledge Objectives
1. 掌握ARM Cortex-M4处理器架构和STM32 HAL库开发模式
2. 理解USB设备协议栈（CDC类）的原理与实现方法
3. 掌握SPI驱动GC9A01圆形屏幕的显示原理和帧缓冲管理
4. 理解I2C总线舵机控制与PID闭环控制的数学模型
5. 掌握6自由度机器人运动学（正运动学计算与坐标变换）
6. 理解帧动画系统和有限状态机在嵌入式中的应用
7. 了解OpenCV计算机视觉（人脸检测）的基本原理（姿态估计为 stretch）
8. 了解LLM大语言模型API调用的流程和语音交互流水线（stretch 选做）

### 技能目标 | Skill Objectives
1. 能够独立搭建STM32CubeIDE开发环境并完成固件编译烧录
2. 能够阅读复杂原理图并理解MCU与各外设模块的连接关系
3. 能够完成贴片IC（含QFN封装）的手工焊接和PCB组装
4. 能够使用ST-Link和串口调试工具进行嵌入式固件调试
5. 能够编写C代码驱动SPI显示屏、I2C舵机控制器、USB设备等外设
6. 能够使用 Python 开发简单上位机（tkinter/PyQt）并通过 USB 桥接与嵌入式设备通信（原项目 Unity 上位机为 stretch 参考）
7. 能够使用OpenCV实现基本的计算机视觉功能（人脸检测为必做，姿态估计为 stretch）
8. 能够集成LLM API实现AI对话和语音交互功能（stretch 选做）

### 素养目标 | Competency Objectives
1. 培养"固件+桌面软件+AI"全栈系统集成的工程思维
2. 培养阅读英文技术文档（Datasheet、Reference Manual）的习惯与能力
3. 培养面对复杂硬件问题时的系统化调试和排错能力
4. 培养项目架构设计意识（模块划分、接口定义、状态管理）
5. 培养技术文档撰写和项目演示表达能力
6. 培养跨学科知识整合能力（电子+机械+软件+AI）

## 课程结构 | Course Structure

### 第一阶段：STM32环境搭建与硬件组装（Day 1-4）
**主题：STM32CubeIDE环境搭建、PCB焊接（贴片IC/QFN封装）、舵机标定、整机组装**

在这一阶段，学员将搭建STM32CubeIDE开发环境，学习ARM Cortex-M4芯片架构和项目工程结构。随后进行PCB焊接训练——包括贴片IC和QFN封装的手工焊接技术，以及自定义舵机驱动板的焊接。完成焊接后进行机械组装、舵机标定和首次上电测试。本阶段对焊接技能要求较高。

In this phase, students set up the STM32CubeIDE development environment, learn the ARM Cortex-M4 architecture and project structure. They then train on PCB soldering -- including manual soldering of SMD ICs and QFN packages, as well as custom servo driver boards. After soldering, students proceed to mechanical assembly, servo calibration, and first power-on testing. This phase has demanding soldering requirements.

### 第二阶段：固件开发与外设驱动（Day 5-8）
**主题：STM32 HAL库编程、USB CDC设备开发、GC9A01圆形屏幕驱动、舵机PID控制、表情动画系统、传感器集成**

这一阶段是项目的核心技术阶段。学员将学习STM32 HAL库编程，开发USB CDC设备实现与PC通信，驱动GC9A01圆形显示屏渲染表情动画，通过I2C总线控制6个舵机并实现PID闭环控制，设计表情状态机和帧动画播放系统，最后集成手势传感器和MPU6050 IMU。

This is the core technical phase. Students learn STM32 HAL library programming, develop a USB CDC device for PC communication, drive the GC9A01 round display for facial expression rendering, control 6 servos via I2C with PID closed-loop control, design expression state machines and frame animation playback, and finally integrate gesture sensors and MPU6050 IMU.

### 第三阶段：Python 上位机、视觉与系统集成（Day 9-12）
**主题：Python 上位机开发、OpenCV 计算机视觉、（stretch）AI 大模型集成、项目展示**

最后阶段转向 PC 端开发。学员用 Python（tkinter/PyQt）做一个简单上位机，通过 USB 桥接控制机器人；再用 OpenCV 实现摄像头人脸检测，让机器人头部跟随人脸。OpenCV 姿态估计、3D 虚拟形象同步、LLM 对话与语音流水线均为 **stretch 选做**。最后做系统整合、展示和技术复盘。

The final phase shifts to PC-side development. Students build a simple Python host app (tkinter/PyQt) that controls the robot over USB, then use OpenCV for camera face detection so the robot's head follows a face. OpenCV pose estimation, 3D avatar sync, LLM dialogue, and the voice pipeline are all **stretch goals**. The phase ends with system integration, presentation, and a technical retrospective.

### 每日课程速览 | Daily Course At-a-Glance

| 天数 | 主题 | 上午 (3h) | 下午 (4h) |
|------|------|----------|----------|
| Day 1 | STM32环境搭建 | ARM Cortex-M4架构 + 项目架构认知 | STM32CubeIDE安装 + 工程创建 + GPIO Blink |
| Day 2 | 硬件原理图阅读 | 原理图阅读方法 + ElectronBot电路分析 | PCB认知 + 3D打印外壳准备 |
| Day 3 | PCB焊接实训 | 贴片IC焊接训练 + QFN封装焊接技巧 | 自定义舵机驱动板焊接 + 焊接质量检查 |
| Day 4 | 机械组装与测试 | 机械结构组装 + 舵机安装 | 舵机标定 + 首次上电测试 + 基础动作验证 |
| Day 5 | 固件基础开发 | STM32 HAL库核心概念 + 工程配置 | USB CDC设备开发 + GC9A01屏幕驱动 |
| Day 6 | 舵机控制系统 | I2C总线通信 + 舵机控制协议 | PID闭环控制 + 6自由度运动学计算 |
| Day 7 | 表情动画系统 | 帧动画原理 + 图像资源制作 | 表情状态机设计 + 动画播放引擎 |
| Day 8 | 传感器集成 | 手势传感器APDS-9960 + MPU6050 IMU | USB摄像头集成 + 传感器数据融合 |
| Day 9 | Python 上位机 | Python GUI（tkinter/PyQt）基础 | USB 桥接通信 + 上位机控制界面 |
| Day 10 | 计算机视觉 | OpenCV 基础 + 人脸检测（Haar 级联） | 人脸跟随 + （stretch）姿态估计 |
| Day 11 | AI 功能集成（stretch） | LLM API 对接 + 对话系统设计（选做） | 语音识别集成 + 自定义行为系统（选做） |
| Day 12 | 项目展示 | 系统最终整合 + Demo 演练 | 项目展示 + 技术复盘 + 创意拓展讨论 |

## 每日时间安排 | Daily Schedule Template

| 时间 | 活动 | 说明 |
|------|------|------|
| 09:00 - 09:15 | 晨间回顾 | 回顾昨日作业，解答疑问 |
| 09:15 - 10:30 | 知识讲解 | 今日核心概念和原理 |
| 10:30 - 10:45 | 课间休息 | |
| 10:45 - 12:00 | 动手实践 | 跟随教程完成代码编写/硬件操作 |
| 12:00 - 13:30 | 午餐休息 | |
| 13:30 - 15:00 | 项目实战 | 将所学应用到ElectronBot项目 |
| 15:00 - 15:15 | 课间休息 | |
| 15:15 - 16:30 | 拓展练习 | 个性化定制和功能拓展 |
| 16:30 - 17:00 | 总结分享 | 今日收获总结、小组分享 |

## 教学方法 | Teaching Methods

1. **项目驱动**：所有知识点围绕ElectronBot项目展开，学以致用，每天都有可见的阶段性成果
2. **分层引导**：核心任务提供详细步骤，进阶任务给方向和提示，创意任务完全自主，适应不同水平学员
3. **即时反馈**：每完成一个模块都能在硬件上看到效果（屏幕点亮、舵机转动、表情播放、视觉响应）
4. **阅读实战**：引导学员阅读STM32 Reference Manual和Datasheet原文，培养英文技术文档阅读能力
5. **系统思维**：强调模块化设计、接口定义和状态管理，而非"堆代码"
6. **同伴学习**：焊接和调试环节鼓励学员互相检查、协作排错

## 前置要求 | Prerequisites
详见 [prerequisites.md](prerequisites.md)

## 评分标准 | Grading Rubric
详见 [grading-rubric.md](grading-rubric.md)

## 作业说明 | Assignments
详见 [assignments.md](assignments.md)

*最后更新：2026-05-27*
