中文 | [English](README_en.md)

# WinUtils

## 项目介绍

C++23 现代Windows微功能组件库，所有功能均同时支持宽窄字节，支持导出为lib或dll

## 功能介绍

1. 轻量命令行解析器，支持多种解析方式
2. 控制台常用功能封装
3. 控制台菜单，支持多级菜单，命令调用
4. HTTP网络库，封装winsock，支持Get、Post方法
5. Dll注入器
6. Windows服务管理
7. 字符串转换
8. 进程/线程/窗口操作
9. 完善单文件日志库
10. INI文件解析
11. 注册表读写
12. ...

## 环境依赖

Visual Studio 2022

## 如何使用

本库支持两种使用方式：

- **静态链接**：将 `WinUtils.lib` 链接到你的项目，运行时不需要额外的 DLL。
- **动态链接**：使用 `WinUtils.dll`，需要确保 DLL 与可执行文件位于同一目录或系统路径中。

#### Visual Studio 配置

1. 选择配置类型：静态库(.lib)或动态库(.dll)
2. 在项目属性中，添加 **附加包含目录**，指向仓库根目录/include。
3. 添加 **附加库目录**，指向编译好的 `WinUtils.lib`/`WinUtils.dll` 所在目录。
4. 在 **附加依赖项** 中添加 `WinUtils.lib`/`WinUtils.dll` 。
5. 如果使用静态库，在`WinUtilsDef.h` 中定义`WU_STATIC`为1。

---

如有更多疑问，欢迎查阅源码或提交 Issue。

## 项目依赖

[mINI](https://github.com/metayeti/mINI)：C++INI解析器（[MIT 许可证](licenses/LICENSE-mINI)）

[WinReg](https://github.com/GiovanniDicanio/WinReg)：C++注册表读写（[MIT 许可证](licenses/LICENSE-WinReg)）


## 许可证

本项目采用 MIT 许可证，详情参见 [LICENSE](LICENSE) 文件。