# 四足机器人控制程序

这是一个基于STC8G单片机的四足机器人控制程序，用于实现机器人的基本运动控制。

## 功能介绍

- **定时器中断**：使用定时器中断实现精确的时间控制。
- **电机控制**：通过PWM信号控制四足机器人的电机，实现腿部的运动。
- **运动模式**：支持两种运动模式：
  - 模式1：渐进式加速运动。
  - 模式2：直接设置角度运动。
- **按键控制**：通过按键选择不同的运动模式和参数。
- **延时功能**：提供精确的延时功能，用于控制运动的节奏。

## 硬件需求

- STC8G系列单片机（或其他兼容型号）
- 四足机器人机械结构（包含电机驱动模块）
- 电源（5V）
- 连接线

## 软件环境

- Keil C51（或其他支持8051单片机的编译器）
- STC-ISP（用于烧录程序到单片机）

## 程序结构

### 主要文件

- **`main.c`**：程序的主文件，包含定时器初始化、引脚配置和主循环。
- **`run.c`**：包含运动控制函数`feet_on`，用于控制机器人的腿部运动。
- **`tool.c`**：包含工具函数，如延时函数、PWM控制函数等。
- **`tool.h`**：头文件，声明了全局变量和函数原型。
- **`run.h`**：头文件，声明了运动控制函数。

### 主要功能模块

- **`Timer0_Init`**：初始化定时器0，用于定时中断。
- **`Delay1ms`**：实现1毫秒的延时函数。
- **`feet_on`**：控制机器人腿部的运动，支持两种模式。
- **`speed`**：通过PWM信号控制电机的速度和角度。
- **`pd`**：更新PWM信号的状态。
- **`sec`**：实现秒级延时功能。

## 使用方法

### 编译与烧录

1. 使用Keil C51打开项目，将所有`.c`文件添加到项目中。
2. 配置项目选项，确保目标设备为STC8G。
3. 编译项目，生成`.hex`文件。
4. 使用STC-ISP将生成的`.hex`文件烧录到单片机中。

### 硬件连接

- 将电机驱动模块的控制引脚连接到单片机的P1^0、P1^1、P1^6、P1^7。
- 确保所有电机的电源和地线连接正确。
- 如果需要按键控制，将按键连接到单片机的其他引脚（如P3^0、P3^1）。

### 运行

1. 为单片机供电，程序将自动运行。
2. 机器人将按照预设的运动模式运动。

Email:17156310913ghj@gmail.com
