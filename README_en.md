English | [中文](README.md)

# WinUtils

## Project Introduction

A modern Windows micro-functionality component library in C++23. All features support both wide and narrow characters, and can be exported as a static library (lib) or dynamic link library (dll).

## Features

1. Lightweight command-line parser supporting multiple parsing methods
2. Encapsulation of common console functions
3. Console menu supporting multi-level menus and command invocation
4. HTTP networking library wrapping Winsock, supporting GET and POST methods
5. DLL injector
6. Windows service management
7. String conversion
8. Process/thread/window operations
9. Comprehensive single-file logging library
10. INI file parser
11. Registry reading/writing
12. ...

## Environment Dependencies

Visual Studio 2022

## How to Use

This library supports two usage methods:

- **Static Linking**: Link `WinUtils.lib` to your project; no additional DLL is required at runtime.
- **Dynamic Linking**: Use `WinUtils.dll`, ensuring the DLL is located in the same directory as the executable or in a system path.

#### Visual Studio Configuration

1. Select the configuration type: Static library (.lib) or Dynamic library (.dll)
2. In the project properties, add **Additional Include Directories** pointing to `include` in the repository root.
3. Add **Additional Library Directories** pointing to the directory containing the compiled `WinUtils.lib`/`WinUtils.dll`.
4. Add `WinUtils.lib`/`WinUtils.dll` to **Additional Dependencies**.
5. If using the static library, define `WU_STATIC` in `WinUtilsDef.h`as 1.

---

If you have further questions, feel free to consult the source code or submit an Issue.

## Project Dependencies

[mINI](https://github.com/metayeti/mINI): C++ INI parser ([MIT License](licenses/LICENSE-mINI))

[WinReg](https://github.com/GiovanniDicanio/WinReg): C++ registry reader/writer ([MIT License](licenses/LICENSE-WinReg))

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.