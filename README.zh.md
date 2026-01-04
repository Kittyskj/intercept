# INTERCEPT

<p align="center">
  <img src="https://img.shields.io/badge/python-3.9+-blue.svg" alt="Python 3.9+">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="MIT License">
  <img src="https://img.shields.io/badge/platform-macOS%20%7C%20Linux-lightgrey.svg" alt="Platform">
</p>

<p align="center">
  <strong>信号情报平台</strong><br>
  面向信号情报工具的 Web 前端。
</p>

<p align="center">
  <img src="static/images/screenshots/screenshot2.png" alt="截图">
</p>

---

## 什么是 INTERCEPT？

INTERCEPT 为信号情报工具提供统一的 Web 界面：

- **寻呼解码** —— 通过 rtl_fm + multimon-ng 支持 POCSAG/FLEX
- **433MHz 传感器** —— 通过 rtl_433 解码气象站、TPMS、IoT 设备
- **飞机跟踪** —— 通过 dump1090 的 ADS-B 实时地图
- **卫星跟踪** —— 使用 TLE 数据预测过境
- **WiFi 侦测** —— aircrack-ng 监控模式扫描
- **蓝牙扫描** —— 设备发现与追踪器检测

---

## 社区

<p align="center">
  <a href="https://discord.gg/z3g3NJMe">加入我们的 Discord</a>
</p>

---

## 快速开始

```bash
git clone https://github.com/smittix/intercept.git
cd intercept
./setup.sh
sudo python3 intercept.py
```

在浏览器中打开 http://localhost:5050。

> **注意：** 需要 Python 3.9+ 以及外部工具。参阅 [Hardware & Installation](docs/HARDWARE.md)。

### 代理与安全控制

外部数据请求（如卫星 TLE 更新）读取标准代理环境变量。启动应用前可设置：

- `INTERCEPT_HTTP_PROXY` / `HTTP_PROXY`
- `INTERCEPT_HTTPS_PROXY` / `HTTPS_PROXY`
- `INTERCEPT_FTP_PROXY` / `FTP_PROXY`
- `INTERCEPT_SOCKS_PROXY` / `SOCKS_PROXY`

还可微调卫星 TLE 请求的安全措施：

- `INTERCEPT_TLE_ALLOWED_HOSTS` —— 允许的主机列表，逗号分隔（默认：CelesTrak 域名）
- `INTERCEPT_TLE_REQUEST_TIMEOUT` —— 请求超时秒数（默认：`10`）
- `INTERCEPT_TLE_MAX_RESPONSE_SIZE` —— 最大响应大小（字节，默认：`1048576`）
- `INTERCEPT_TLE_USER_AGENT` —— 自定义 User-Agent 头

代理变量的大小写均被接受。

---

## 要求

- **Python 3.9+**
- **SDR 硬件** —— RTL-SDR（约 $25）、LimeSDR 或 HackRF
- **外部工具** —— rtl-sdr、multimon-ng、rtl_433、dump1090、aircrack-ng

快速安装（Ubuntu/Debian）：
```bash
sudo apt install rtl-sdr multimon-ng rtl-433 dump1090-mutability aircrack-ng bluez
```

详见 [Hardware & Installation](docs/HARDWARE.md)。

---

## 文档

| 文档 | 说明 |
|------|------|
| [Features](docs/FEATURES.md) | 全部功能列表 |
| [Usage Guide](docs/USAGE.md) | 各模式的详细指引 |
| [Troubleshooting](docs/TROUBLESHOOTING.md) | 常见问题解决方案 |
| [Hardware & Installation](docs/HARDWARE.md) | SDR 硬件与工具安装 |

---

## 开发

本项目在 AI 协助下完成开发，旨在通过简洁统一的界面让 Software Defined Radio 更易用。

欢迎贡献和改进。

---

## 免责声明

**本软件仅用于教育目的。**

- 仅在获得适当授权时使用
- 未经同意拦截通信可能违法
- WiFi/蓝牙攻击需明确许可
- 遵守相关法律责任自负

---

## 许可证

MIT 许可证 —— 见 [LICENSE](LICENSE)

## 作者

作者 **smittix** —— [GitHub](https://github.com/smittix)

## 鸣谢

[rtl-sdr](https://osmocom.org/projects/rtl-sdr/wiki) |
[multimon-ng](https://github.com/EliasOenal/multimon-ng) |
[rtl_433](https://github.com/merbanan/rtl_433) |
[dump1090](https://github.com/flightaware/dump1090) |
[aircrack-ng](https://www.aircrack-ng.org/) |
[Leaflet.js](https://leafletjs.com/) |
[Celestrak](https://celestrak.org/)
