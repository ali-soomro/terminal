# terminal — Cutefish Terminal Emulator

## Purpose
Terminal emulator for CutefishOS, bundling qmltermwidget (from Swordfish90/qmltermwidget) as a subproject.

## Build
```bash
cmake -B build -DCMAKE_INSTALL_PREFIX=/usr && cmake --build build && sudo cmake --install build
```

## Dependencies
- Qt6 (Core, Core5Compat, Gui, Quick, QuickControls2, Widgets, DBus, LinguistTools)

## Structure
- `src/main.cpp` — entry point
- `src/processhelper.cpp/h` — process management
- `src/utils.cpp` — utilities
- `src/fonts.cpp` — font configuration
- `qmltermwidget/` — bundled terminal widget subproject
  - `qmltermwidget/lib/` — terminal emulation library
  - `qmltermwidget/src/` — QML terminal widget

## Install Targets
- Binary → `/usr/bin`
- Desktop file `cutefish-terminal.desktop` → `/usr/share/applications/`
- Translations → `/usr/share/cutefish-terminal/translations/`

## Qt5→Qt6 Migration Notes
- Qt5 → Qt6
- `QRegExp` → `QRegularExpression`
- `QTextCodec` moved to `Qt6Core5Compat`
- `QProcess::setupChildProcess` → `setChildProcessModifier` (lambda-based)
- `wchar_t` → `quint16` in Character type

## Status
✅ Ported, built, installed, pushed (github.com/ali-soomro)
