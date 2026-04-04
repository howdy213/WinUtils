中文 | [English](README_en.md)
# WinUtils

## 项目介绍

C++23 现代 Windows 微功能组件库，所有功能均同时支持宽窄字节，支持导出为静态库（.lib）或动态库（.dll）。

## 功能介绍

1. 轻量命令行解析器，支持多种解析方式
2. 控制台常用功能封装
3. 控制台菜单，支持多级菜单与命令调用
4. HTTP 网络库，封装 WinSock2，支持 GET、POST 方法
5. DLL 注入器
6. Windows 服务管理
7. 字符串转换
8. 进程/线程/窗口操作
9. 完善的单文件日志库
10. INI 文件解析（基于 mINI 库）
11. 注册表读写（基于 WinReg 库）
12. 更多实用功能...

## 环境依赖

- Visual Studio 2022（MSVC 编译器，需支持 C++23 标准）
- Windows SDK

## 如何使用

本库支持两种使用方式：

- **静态链接**：将 `WinUtils.lib` 链接到你的项目，运行时不需要额外的 DLL。
- **动态链接**：使用 `WinUtils.dll`，需要确保 DLL 与可执行文件位于同一目录或系统路径中。

### Visual Studio 配置步骤

1. 打开项目属性，选择配置类型：静态库（.lib）或动态库（.dll）。
2. 在 **C/C++ → 常规 → 附加包含目录** 中添加仓库根目录下的 `include` 文件夹。
3. 在 **链接器 → 常规 → 附加库目录** 中添加编译生成的 `WinUtils.lib`（或 `WinUtils.dll`）所在目录。
4. 在 **链接器 → 输入 → 附加依赖项** 中添加 `WinUtils.lib`（静态链接）或 `WinUtils.dll`（动态链接）。
5. （可选）通过预处理器宏定义启用特定特性：  
   在项目 **C/C++ → 预处理器 → 预处理器定义** 中添加以下宏，或在包含头文件之前 `#define` 它们。

#### 支持的宏定义

| 宏名称                       | 作用                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| `WU_DYNAMIC_LINK`            | 使用动态链接（需配合 DLL）。若不定义，默认为静态链接。        |
| `WU_NARROW_STRING`           | 使用窄字符串，**不推荐** |
| `WU_NO_INI_CASE_SENSITIVE`   | 使 INI 解析器大小写不敏感（仅影响 `ini.h`）。默认大小写敏感。 |


## 项目依赖

- [mINI](https://github.com/metayeti/mINI)：C++ INI 解析器（[MIT 许可证](licenses/LICENSE-mINI)）
- [WinReg](https://github.com/GiovanniDicanio/WinReg)：C++ 注册表读写库（[MIT 许可证](licenses/LICENSE-WinReg)）

## 许可证

本项目采用 MIT 许可证，详情参见 [LICENSE](LICENSE) 文件。