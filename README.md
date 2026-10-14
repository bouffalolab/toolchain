这是一个**交叉编译工具链（Toolchain）发布仓库**的描述，通常用于为嵌入式开发、RISC-V 生态或 Zephyr RTOS 项目提供预编译的 GCC 工具链。 Bouffalo sdk使用这些工具链。

## 仓库概览

该仓库的 **Releases 页面**会按版本发布预编译的工具链二进制包，覆盖主流桌面操作系统与 CPU 架构组合。

### 支持平台矩阵

| 工具链 | MacOS (Apple Silicon) | Linux (ARM64) | Linux (x86_64) | Windows (x86_64) |
|---|---|---|---|---|
| **XuanTie-gcc** | ✅ | ❎ | ✅ | ✅ |
| **Zephyr-gcc** | ✅ | ✅ | ✅ | ✅ |

### 说明

- **XuanTie-gcc**：面向平头哥（T-Head）玄铁 RISC-V 系列处理器的 GCC 工具链，常用于玄铁开发板、RISC-V MCU/SoC 的裸机或 RTOS 开发。
- **Zephyr-gcc**：面向 Zephyr RTOS 的 GCC 工具链，用于编译 Zephyr 支持的各类架构（ARM、RISC-V、x86 等）目标。
