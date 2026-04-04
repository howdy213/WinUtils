# WinUtils

## Project Introduction

WinUtils is a modern C++23 library of lightweight Windows utility components. All features support both narrow and wide character strings, and the library can be exported as a static library (.lib) or a dynamic library (.dll).

## Features

1. Lightweight command-line parser with multiple parsing modes
2. Encapsulation of common console functions
3. Console menu supporting multi-level menus and command invocation
4. HTTP networking library wrapping WinSock2, supporting GET and POST methods
5. DLL injector
6. Windows service management
7. String conversion utilities
8. Process / thread / window operations
9. Comprehensive single-file logging library
10. INI file parsing (based on the mINI library)
11. Registry reading/writing (based on the WinReg library)
12. Many more practical utilities...

## Environment Dependencies

- Visual Studio 2022 (MSVC compiler with C++23 standard support)
- Windows SDK

## How to Use

This library supports two usage methods:

- **Static linking**: Link `WinUtils.lib` into your project; no additional DLL is required at runtime.
- **Dynamic linking**: Use `WinUtils.dll`; ensure the DLL is located in the same directory as the executable or in a system path.

### Visual Studio Configuration Steps

1. Open the project properties and select the configuration type: Static library (.lib) or Dynamic library (.dll).
2. In **C/C++ → General → Additional Include Directories**, add the `include` folder located at the repository root.
3. In **Linker → General → Additional Library Directories**, add the directory containing the compiled `WinUtils.lib` (or `WinUtils.dll`).
4. In **Linker → Input → Additional Dependencies**, add `WinUtils.lib` (for static linking) or `WinUtils.dll` (for dynamic linking).
5. (Optional) Enable specific features using preprocessor macros:  
   Add the following macros in **C/C++ → Preprocessor → Preprocessor Definitions**, or `#define` them before including the headers.

#### Supported Macros

| Macro Name                 | Effect                                                       |
| -------------------------- | ------------------------------------------------------------ |
| `WU_DYNAMIC_LINK`          | Use dynamic linking (requires the DLL). If not defined, static linking is used by default. |
| `WU_NARROW_STRING`         | Use narrow character strings. **Not recommended**            |
| `WU_NO_INI_CASE_SENSITIVE` | Makes the INI parser case‑insensitive (affects `ini.h` only). Default is case‑sensitive. |

## Project Dependencies

- [mINI](https://github.com/metayeti/mINI): C++ INI parser ([MIT License](licenses/LICENSE-mINI))
- [WinReg](https://github.com/GiovanniDicanio/WinReg): C++ registry read/write library ([MIT License](licenses/LICENSE-WinReg))

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.