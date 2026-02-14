# Building scetool with Visual Studio 2019

This project has been set up with a Visual Studio 2019 solution (`scetool.sln`) and project (`scetool.vcxproj`).

## Dependencies

### zlib
`scetool` requires `zlib`. The project is configured to:
1. Include headers from the project root (where `zlib.h` and `zconf.h` are located).
2. Link against `zlib.lib`.

You will need to provide `zlib.lib`. You can:
- **Fastest way**: Download a precompiled `zlib.lib` and place it directly in the project root folder (next to `scetool.sln`). The project is configured to look for it there.
- Use a package manager like [vcpkg](https://github.com/microsoft/vcpkg): `vcpkg install zlib:x64-windows` (or `x86-windows`).
- Use NuGet to install a zlib package.
- Manually download/build zlib and add its path to the project's **Library Directories**.

### How to build zlib manually for scetool:
1. Download zlib source from [zlib.net](https://zlib.net/).
2. Open the **correct** Visual Studio terminal:
   - For **x64**: "x64 Native Tools Command Prompt for VS 2019".
   - For **x86**: "x86 Native Tools Command Prompt for VS 2019".
3. Navigate to zlib folder and run: `nmake -f win32/Makefile.msc`.
4. Copy the resulting `zlib.lib` to the `scetool` root folder.

## Configuration

The project supports:
- **Debug** and **Release** configurations.
- **x86** (Win32) and **x64** platforms.

## Preprocessor Definitions

The following definitions are included:
- `_CRT_SECURE_NO_WARNINGS`: To suppress warnings about "insecure" C functions (like `fopen`, `strcpy`).
