# Changelog
All notable changes to this project will be documented here.

## [0.1.0] - Initial Release
- First version of Dcode language
- Colon-based syntax introduced
- first instructon set introduced


## [0.2.0] - 2026-05-30
### Added
- **AI Lifecycle Commands**
  - `ai:create:model`, `ai:train`, `ai:evaluate`, `ai:visualize`, `ai:run`, `ai:test`, `ai:status`, `ai:reset`
- **Persistence**
  - `ai:save`, `ai:load`, `ai:export`, `ai:import`, `ai:share`
- **Device Control**
  - `ai:set:device <CPU|GPU|NPU>`
- **Dataset Handling**
  - `ai:load:dataset path=<file>`
- **Executor IDE Features**
  - Clear button (`clear_console`) to wipe OutputConsole
  - Line numbers in output for better debugging
  - Multi‑model support (`name=ModelA`, `model=ModelA`)
  - Improved error handling with line numbers + suggestions
  - Optional Stop button for interrupting long runs

### Changed
- Output formatting now includes line numbers.
- Error messages are more descriptive (invalid command, missing model).
- AI commands now support named models instead of a single global model.

### Fixed
- Removed invalid `line.string()` call → replaced with `line.strip_edges().is_empty()`.
- Signal connections updated for Godot 4 (`run_button.pressed.connect(run_code)`).

 ## [1.0.0] - first major release
### Added

### Core
- Fixed missing function stubs (`_ai_save`, `_ai_load`, etc.) → no more “function not found” errors.
- Unified dispatcher with consistent argument parsing (`key=value`).
- Added structured dictionary output for AI commands.
- Improved math handling inside `print:` (supports `add`, `sub`, `mul`, `div`, `pow`, `sqrt`, `rand`, `expression`).

### Genesis Extras
- **Agents**: create, bind, voice, emotion, wake, dialogue, list, status, assign, delete.
- **Voice**: enable, listen, recognize, speak, dialogue, device list, wake, emotion, mute/unmute.
- **Export**: exe, apk, bin, app, multi-target, installer, publish, status, reset, clean.
- **System**: time, date, status, reset.
- **Loops & Delay**: `loop:for`, `loop:while`, `delay:ms`.
- **Plugins & Libraries**: import, load/bind, list, remove.

### Internal
- Added registries for plugins (`plugins`) and libraries (`libraries`).
- `list` now shows loaded items.
- `remove` erases entries.
