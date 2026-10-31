# 第三方组件与许可证说明

本项目自身代码使用 MIT License（见 `LICENSE`）。

## 源码依赖

- **EUI-NEO** — Apache License 2.0，https://github.com/sudoevolve/EUI-NEO
- **GLFW** — zlib/libpng License
- **glad** — MIT / Khronos 许可
- **FreeType** — FreeType License (FTL) / GPLv2
- **libpng** — libpng License
- **md4c** — MIT License
- **zlib** — zlib License

以上组件位于 `third_party/`，各自保留原始版权与许可证文件。

## 发布包内的第三方程序

`assets\roottool\`、`assets\scrcpy\` 与 `assets\apk\` 中包含第三方二进制：

- **adb** — Android SDK Platform Tools，Apache License 2.0
- **scrcpy** — Apache License 2.0，https://github.com/Genymobile/scrcpy
- **ksud / Neo10-Root** — 由相应项目按其许可证分发
- **KernelSU / KernelSU Next / SukiSU / 7kimi SU APK** — 由各自上游项目按其许可证分发，本项目不修改这些 APK

发布时请保留各上游项目的许可证与来源说明；如果重新分发 APK，请同时遵守对应项目的许可证。
