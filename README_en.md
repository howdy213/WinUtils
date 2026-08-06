[中文](README.md) | English

# WinUtils

## Project Introduction

A modern C++23 micro-utility component library for Windows. All features support both wide and narrow character strings. It can be exported as a static library (.lib) or a dynamic library (.dll).

## Features

1. Lightweight command-line parser with multiple parsing modes
2. Common console utility wrappers
3. Console menu system with multi-level menus and command invocation
4. HTTP network library wrapping WinSock2, supporting GET and POST methods
5. DLL injector
6. Windows service management
7. String conversion
8. Process / thread / window operations
9. Comprehensive single-header logging library
10. INI file parsing (based on the mINI library)
11. Registry read/write (based on the WinReg library)
12. Inter-process communication (based on the libsharedmemory library)
13. And more useful utilities...

## Environment Requirements

- Visual Studio 2022 (MSVC compiler, must support the C++23 standard)
- Windows SDK

## How to Use

The library supports two usage modes:

- **Static linking**: Link `WinUtils.lib` to your project. No extra DLL is required at runtime.
- **Dynamic linking**: Use `WinUtils.dll`. The DLL must be placed in the same directory as the executable or in a system path.

### Visual Studio Configuration Steps

1. Open the project properties and select the configuration type: static library (.lib) or dynamic library (.dll).
2. Under **C/C++ → General → Additional Include Directories**, add the `include` folder located in the repository root.
3. Under **Linker → General → Additional Library Directories**, add the directory containing the generated `WinUtils.lib` (or `WinUtils.dll`).
4. Under **Linker → Input → Additional Dependencies**, add `WinUtils.lib` (for static linking) or `WinUtils.dll` (for dynamic linking).
5. (Optional) Define preprocessor macros to enable specific features:  
   Add the macros below in **C/C++ → Preprocessor → Preprocessor Definitions**, or `#define` them before including the header files.

#### Supported Macro Definitions

| Macro Name                 | Purpose                                                      |
| -------------------------- | ------------------------------------------------------------ |
| `WU_DYNAMIC_LINK`          | Use dynamic linking (requires the DLL). If not defined, static linking is used by default. |
| `WU_NARROW_STRING`         | Use narrow character strings (**not recommended**)           |
| `WU_NO_INI_CASE_SENSITIVE` | Make the INI parser case-insensitive (only affects `ini.h`). The default is case-sensitive. |

## Project Dependencies

- [mINI](https://github.com/metayeti/mINI): C++ INI parser ([MIT License](licenses/LICENSE-mINI))
- [WinReg](https://github.com/GiovanniDicanio/WinReg): C++ registry read/write library ([MIT License](licenses/LICENSE-WinReg))
- [libsharedmemory](https://github.com/kyr0/libsharedmemory): C++ inter-process communication library ([MIT License](licenses/LICENSE-libsharedmemory))

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.