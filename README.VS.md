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

## Configuration

The project supports:
- **Debug** and **Release** configurations.
- **x86** (Win32) and **x64** platforms.

## Preprocessor Definitions

The following definitions are included:
- `_CRT_SECURE_NO_WARNINGS`: To suppress warnings about "insecure" C functions (like `fopen`, `strcpy`).
