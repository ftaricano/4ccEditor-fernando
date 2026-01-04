# Repository Guidelines

## Project Structure & Module Organization
This is a native Windows C++ (Win32) application.
- Source code lives at the repo root: `main.cpp`, `window.cpp`, `*.cpp`, `*.h`.
- Resources and UI definitions: `resource.rc`, `resource.h`.
- Assets: `*.bmp`, `*.ico`.
- Built artifacts land in `Release\` (e.g., `Release\4ccEditor.exe`, `Release\lib\*.dll`).
- Third-party libraries and tools are stored in `lib\` and bundled folders (e.g., `pesXcrypter3.0.0`).

## Build, Test, and Development Commands
Use Visual Studio Build Tools (Win32 config only).
```bat
"C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\Common7\Tools\VsDevCmd.bat" -arch=x86 -host_arch=x64
msbuild 4ccEditor.vcxproj /p:Configuration=Release /p:Platform=Win32
```
Run the app from `Release\4ccEditor.exe`. Ensure required DLLs exist under `Release\lib\` (e.g., `libpesXcrypter.dll`; `libpes15crypter.dll` is optional).

## Coding Style & Naming Conventions
- Keep the existing formatting (tabs for indentation in `.cpp/.h` files).
- Win32 control IDs follow patterns like `IDT_` (edit), `IDC_` (updown), `IDB_` (button).
- Use concise, descriptive function names; avoid introducing new naming schemes.

## Testing Guidelines
There is no automated test framework in this repository. Validate changes manually in the UI, especially for edits that touch `window.cpp` or `resource.rc`.

## Commit & Pull Request Guidelines
Commit messages in history follow a short, descriptive pattern such as:
- `Season Year Edition (Version X)` (e.g., “Autumn 25 Edition (Version A)”)
- `Prepare 4ccEditor build`
Use the same style: single-line summary, title case, no ticket prefixes.
PRs should include:
- A brief summary of UI or behavior changes.
- Screenshots for UI changes (before/after when relevant).
- Notes on build/config used (e.g., Release|Win32).
