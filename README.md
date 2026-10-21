# Bouffalo Lab Toolchain

本仓库用于发布 Bouffalo Lab SDK、玄铁（XuanTie）RISC-V 处理器及 Zephyr RTOS 开发所需的预编译 GCC 交叉编译工具链。仓库中只包含发布说明，工具链二进制文件通过 GitHub Releases 提供。

当前 Release：[`default`](https://github.com/bouffalolab/toolchain/releases/tag/default)

## 版本与支持平台

| 工具链 | 版本 | macOS ARM64 | Linux ARM64 | Linux x86_64 | Windows x86_64 |
|---|---|:---:|:---:|:---:|:---:|
| XuanTie GCC | v2.10.2 | 支持 | 支持 | 支持 | 支持 |
| XuanTie GCC | v2.6.1 | — | — | 支持 | 支持 |
| Zephyr GCC RISC-V | 1.0.0-rc1 | 支持 | 支持 | 支持 | 支持 |

> 表中的平台指运行工具链的**主机平台**。Zephyr 发布文件在 Linux ARM64 资产中使用 `aarch64` 命名。

## 下载

### XuanTie GCC

面向平头哥（T-Head）玄铁 RISC-V 系列处理器。

| 版本 | 主机平台 | 发布文件 | 大小 |
|---|---|---|---:|
| v2.10.2 | macOS ARM64 | [xuantie-gcc-riscv-v2.10.2-macos-arm64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/xuantie-gcc-riscv-v2.10.2-macos-arm64.tar.xz) | 66.1 MiB |
| v2.10.2 | Linux ARM64 | [xuantie-gcc-riscv-v2.10.2-linux-arm64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/xuantie-gcc-riscv-v2.10.2-linux-arm64.tar.xz) | 83.8 MiB |
| v2.10.2 | Linux x86_64 | [xuantie-gcc-riscv-v2.10.2-linux-x86_64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/xuantie-gcc-riscv-v2.10.2-linux-x86_64.tar.xz) | 87.7 MiB |
| v2.10.2 | Windows x86_64 | [xuantie-gcc-riscv-v2.10.2-windows-x86_64.7z](https://github.com/bouffalolab/toolchain/releases/download/default/xuantie-gcc-riscv-v2.10.2-windows-x86_64.7z) | 36.9 MiB |
| v2.6.1 | Linux x86_64 | [xuantie-gcc-riscv-v2.6.1-linux-x86_64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/xuantie-gcc-riscv-v2.6.1-linux-x86_64.tar.xz) | 94.8 MiB |
| v2.6.1 | Windows x86_64 | [xuantie-gcc-riscv-v2.6.1-windows-x86_64.7z](https://github.com/bouffalolab/toolchain/releases/download/default/xuantie-gcc-riscv-v2.6.1-windows-x86_64.7z) | 73.4 MiB |

### Zephyr GCC RISC-V

面向 Zephyr RTOS 的 RISC-V 交叉编译工具链。

| 版本 | 主机平台 | 发布文件 | 大小 |
|---|---|---|---:|
| 1.0.0-rc1 | macOS ARM64 | [zephyr-gcc-riscv-1.0.0-rc1-macos-aarch64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/zephyr-gcc-riscv-1.0.0-rc1-macos-aarch64.tar.xz) | 125.3 MiB |
| 1.0.0-rc1 | Linux ARM64 | [zephyr-gcc-riscv-1.0.0-rc1-linux-aarch64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/zephyr-gcc-riscv-1.0.0-rc1-linux-aarch64.tar.xz) | 123.4 MiB |
| 1.0.0-rc1 | Linux x86_64 | [zephyr-gcc-riscv-1.0.0-rc1-linux-x86_64.tar.xz](https://github.com/bouffalolab/toolchain/releases/download/default/zephyr-gcc-riscv-1.0.0-rc1-linux-x86_64.tar.xz) | 144.7 MiB |
| 1.0.0-rc1 | Windows x86_64 | [zephyr-gcc-riscv-1.0.0-rc1-windows-x86_64.7z](https://github.com/bouffalolab/toolchain/releases/download/default/zephyr-gcc-riscv-1.0.0-rc1-windows-x86_64.7z) | 117.3 MiB |

## 安装

1. 根据主机操作系统和 CPU 架构下载对应资产。
2. 校验文件完整性（SHA-256 见下一节）。
3. 解压工具链。Linux 和 macOS 的 `.tar.xz` 文件可直接解压：

   ```bash
   mkdir -p "$HOME/toolchains"
   tar -xf <发布文件>.tar.xz -C "$HOME/toolchains"
   ```

   Windows 的 `.7z` 文件可使用 [7-Zip](https://www.7-zip.org/) 解压。

4. 将解压目录中的 `bin` 加入 `PATH`。例如：

   ```bash
   export PATH="$HOME/toolchains/<解压目录>/bin:$PATH"
   ```

   Windows 可通过“系统属性 → 环境变量”将对应 `bin` 目录加入 `Path`。

5. 运行 `<target>-gcc --version`，确认工具链可执行文件已被正确识别。

## SHA-256 校验

| 发布文件 | SHA-256 |
|---|---|
| `xuantie-gcc-riscv-v2.10.2-macos-arm64.tar.xz` | `3a950464d6f93cd17af27401e4156ccc9e743d4dc5f39010440af4abefd8705b` |
| `xuantie-gcc-riscv-v2.10.2-linux-arm64.tar.xz` | `9f19c300979d5e7189b9630c4480f5690b93c8e840a767dd4ef61bf5a6565c8e` |
| `xuantie-gcc-riscv-v2.10.2-linux-x86_64.tar.xz` | `a3a6fd5fe9fce64c09fb6d96cb1075ba114ee466d73bba6be5a4462fee978c83` |
| `xuantie-gcc-riscv-v2.10.2-windows-x86_64.7z` | `373babef6d84b78047fe3bd7ffce318d81bf7df54fa9be6feaf0863d4f800994` |
| `xuantie-gcc-riscv-v2.6.1-linux-x86_64.tar.xz` | `83817bd7cab693fc249bb98869de5e475c1ede577f4a188869fed96c8dbb8e1a` |
| `xuantie-gcc-riscv-v2.6.1-windows-x86_64.7z` | `36daf2bc92f0161c9db1840d3c1b9de2db950d796f2920e6bc6188e9893a57ca` |
| `zephyr-gcc-riscv-1.0.0-rc1-macos-aarch64.tar.xz` | `c3590c44882adea9f8bc29c4605dc2cf57029ae23646a1017b8cb54e5a57aedb` |
| `zephyr-gcc-riscv-1.0.0-rc1-linux-aarch64.tar.xz` | `f636142093a792f2c76a08fb243427fcdde7939596dc140cdcb50456916f581e` |
| `zephyr-gcc-riscv-1.0.0-rc1-linux-x86_64.tar.xz` | `01750834c471fbdb335c1b8b8aee17010a1968938957db85640c366235771a38` |
| `zephyr-gcc-riscv-1.0.0-rc1-windows-x86_64.7z` | `ba1a746f33046998080d8a68d954ed108b908b53896487bf252b8d4a1afd3d74` |

Linux 下可使用 `sha256sum <发布文件>` 校验，macOS 下可使用 `shasum -a 256 <发布文件>`，Windows PowerShell 下可使用：

```powershell
(Get-FileHash .\<发布文件> -Algorithm SHA256).Hash.ToLower()
```
