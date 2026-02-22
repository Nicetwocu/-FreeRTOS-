# 基于 W5500+FreeRTOS 的工业数字量采集模块

本项目是一个 **8 路光耦隔离数字量输入采集卡**，通过以太网（Modbus TCP）或 RS-232（Modbus RTU/自定义协议）实时监控工业现场设备状态。采用 STM32F103VET6 主控 + W5500 硬件协议栈芯片，在 FreeRTOS 上实现多任务协同，适用于工业自动化、设备状态监测等场景。

## 主要功能
- **8 路数字量输入**：光耦隔离（EL357），24V 工业电平，RC 滤波抗干扰
- **以太网通信**：基于 W5500 硬件 TCP/IP 协议栈，Modbus TCP 服务器（端口 8000）
- **RS-232 接口**：支持 Modbus RTU 从站和自定义协议（用于设备配置）
- **多协议支持**：可切换运行模式（Modbus TCP/RTU、自定义协议）
- **实时操作系统**：FreeRTOS 任务划分（DI 扫描、网络处理、协议转换）
- **配置灵活**：上电未配置时自动请求参数，支持动态模式切换

## 技术栈
- **硬件**：STM32F103VET6 + W5500 + EL357 + HR911105A + LM2596 + AMS1117
- **软件**：FreeRTOS (CMSIS-RTOS v2) + W5500 ioLibrary + Modbus 协议栈
- **工具**：Keil MDK、Altium Designer、Modbus Poll、Wireshark
