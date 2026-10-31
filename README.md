# Min RooT

Windows 桌面端的 Android Root 管理器安装 / 切换 / 提权辅助工具，使用 C++17 + [EUI-NEO](https://github.com/sudoevolve/EUI-NEO)（GLFW + OpenGL）自绘界面。

> 仅用于本人拥有并授权的设备。请遵守设备厂商、Root 管理器及所在地区的相关法律法规。

## 功能

- 内置 KernelSU、KernelSU Next、SukiSU、7kimi SU 四个管理器的安装入口
- 管理器安装包只从 `assets\apk\` 读取，文件名固定，替换同名 APK 即可更新，不依赖联网下载
- 设备检测、管理器安装状态 / 版本检测
- 检查本地安装包与设备已装版本，弹窗批量安装 / 更新
- 调用 Neo10-Root 提权脚本、日志查看与导出
- 原生 Windows 标题栏、明暗主题、单实例限制

## 下载

请到仓库的 **Releases** 页面下载：

- `MinRooT-v3.2.0-win64.zip`：Windows 64 位免安装版，解压即用

## 运行

1. 解压到一个非中文、非只读目录（例如 `D:\MinRooT`）
2. 双击 `Min RooT.exe`，建议右键“以管理员身份运行”
3. 保持 `assets\` 与 exe 在同一层；首次运行会自动生成 `config.ini`、`logs\`、`temp\`
4. 手机开启 USB 调试并授权后，在“管理器”页检测设备

## 管理器安装包命名

`assets\apk\` 下使用固定文件名：

| 管理器 | 文件名 |
| --- | --- |
| KernelSU | `KSU.apk` |
| KernelSU Next | `KSU-N.apk` |
| SukiSU | `SukSU.apk` |
| 7kimi SU | `7k.apk` |

以后更新管理器时，只需要把新 APK 改成上述名字并覆盖旧文件，不需要重新编译。

## 从源码构建

环境：

- Windows 10/11 x64
- Visual Studio 2022 Build Tools（MSVC x64）
- CMake 3.22+
- Ninja
- 支持 OpenGL 3.3 的显卡驱动

```bat
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release
cmake --build build --parallel
```

产物为 `build\SiliconRootTool.exe`。构建后的 `POST_BUILD` 会把 `assets\` 与 `author.ini` 复制到输出目录。

## 目录

```
EuiRoot/
├── CMakeLists.txt
├── README.md
├── LICENSE
├── src/                 应用源码
├── third_party/         EUI-NEO 等第三方源码
├── assets/              字体、图标、运行时资源
│   ├── apk/             四个管理器 APK（发布包内提供）
│   ├── roottool/        Neo10-Root 提权工具（发布包内提供）
│   └── scrcpy/          投屏组件（发布包内提供）
└── docs/                设计说明与截图
```

第三方二进制（adb / scrcpy / ksud / APK）体积较大，源码仓库不包含，统一放在 Release 包中。

## 许可证

本项目代码使用 MIT License，见 [LICENSE](LICENSE)。`third_party/` 下的组件保留各自许可证，详见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
