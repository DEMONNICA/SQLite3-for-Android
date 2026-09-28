> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.53.4] - `2026-07-24`
>
> - Added Axeron plugin mode support — module can now be installed as a standalone module or as an Axeron plugin.
> - Added `AxManager` detection in `detect_root_all` for plugin mode root identification.
> - Added `action.sh` for manual database optimization via Action button — runs `optimize.sh` in background with enhanced sqlite3 memory flags.
> - Added dynamic `MMAP_SIZE` in `optimize.sh` based on available RAM for adaptive memory allocation.
> - Added auto-detection of plugin/module path in `optimize.sh` based on Axeron environment.
> - Added `renice -n 19` and `ionice -c 3` in `optimize.sh` to reduce lag during optimization.
> - Added `PRAGMA optimize` to database optimization routine in `optimize.sh`.
> - Added temp file-based processing in `optimize.sh` to fix word splitting on paths with spaces.
> - Added `Aster` (`me.yuki.aster`) detection to APatch variants in `detect_root_all` in `customize.sh`.
> - Added `sys.boot_completed` check with `sleep 30` in `service.sh` before running `optimize.sh`.
> - Added `sync` in `service.sh` after module.prop update and in `optimize.sh` before fstrim.
> - Added `sm fstrim` and block-level fstrim to `uninstall.sh`.
> - Added `/data/local/tmp` to cleanup list in `uninstall.sh`.
> - Added `axeronPlugin=666` to `module.prop`.
> - Added `ram_label()` function in `device_info()` in `customize.sh` for cleaner RAM label calculation.
> - Added SDK numeric validation in `device_info()` in `customize.sh`.
> - Added author verification against `@illumi` in `verify_module_id()` in `verify.sh`.
> - Added cleanup of temp files after optimization in `optimize.sh`.
> - Changed SQLite3 version to `3.53.4 [2026-07-24 19:02:57]`.
> - Changed `description` in `module.prop`.
> - Changed `detect_root_all` in `customize.sh` to loop-based detection with order APatch → KernelSU → Magisk.
> - Changed `.method` reading order in `service.sh` to APatch → KernelSU → Magisk, with APatch now reading 5 lines including `APATCH_APP_VER`.
> - Changed backup path from `system/bin/sqlite3.bak` to `backup/sqlite3` in `customize.sh` and `uninstall.sh`.
> - Changed `Info` bubble replacing `Storage:Fstrim completed` in system notification in `optimize.sh`.
> - Fixed `ORPHAN`, `DB_ORPHAN`, `SUCCESS`, `FAILED`, and `CORRUPT` counters in `optimize.sh` always returning `0` due to subshell variable scope — now uses temp files for accurate count.
> - Fixed databases with custom collation sequences being incorrectly counted as corrupt in `optimize.sh`.
> - Fixed `verify.sh` stripping spaces from ZIP path via `clean_path()`.
> - Removed `.method` file deletion from `uninstall.sh`.
---

> [3.53.0] - `2026-04-09`
>
> - Added system package exclusion — only third-party apps are force-stopped during optimization.
> - Added backup confirmation message in `customize.sh`.
> - Changed SQLite3 version to `3.53.0 [2026-04-09 11:41:38]`.
> - Changed banner image and SQLite version string in `README.md`.
> - Fixed `optimize.sh` force-stop incorrectly targeting system packages causing volume lock bug.
> - Fixed `MODDIR` in `uninstall.sh` to use `readlink -f` for correct path resolution.
> - Fixed typo `post_install_actions` → `post_install_action` in `customize.sh`.
> - Removed `SKIPUNZIP=1` and `DEBUG=false` from `customize.sh`.
---

> [3.51.3] - `2026-03-13`
>
> - Added `FolkLite` (`mi.yuki.folk`) detection to `detect_root_all`.
> - Added backup of original `/system/bin/sqlite3` before replacing.
> - Added automatic restore of original `sqlite3` on uninstall via `uninstall.sh`.
> - Added numbered comments throughout `customize.sh` for better readability.
> - Added `optimize.sh` for post-reboot database optimization — WAL checkpoint, VACUUM, ANALYZE, and integrity check on all system databases.
> - Added orphan WAL/SHM and uninstalled app database cleanup in `optimize.sh`.
> - Added fstrim on `/data`, `/user`, and `/cache` after optimization.
> - Added system notification when optimization is complete.
> - Changed structure of `README.md` for a better impression.
> - Changed `README.md` description and feature list.
> - Changed `customize.sh` and `verify.sh` for better future performance.
> - Changed `service.sh` to run `optimize.sh` via `setsid` after reboot.
> - Changed `customize.sh` ABI detection and file extraction based on architecture.
> - Changed `detect_root_all` to match latest root manager variants.
> - Changed `set_donate_link` timezone detection with multiple fallbacks.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Removed `action.sh`, replaced by `optimize.sh`.
> - License changes.
---

> [3.51.2] - `2026-01-09`
>
> - Added `action.sh` to check for the latest version of `sqlite3`.
> - Added deletion code for `.method` file in `uninstall.sh`.
> - Changed SQLite3 version to `3.51.2 [2026-01-09 17:27:48]`.
> - Changed code improvements in `customize.sh`.
> - Changed `verify.sh` for stronger module security improvements.
> - Removed `notification` and some minor changes in `service.sh`.
---

> [3.51.1] - `2025-11-28`
>
> - Changed SQLite3 version to `3.51.1 [2025-11-28 17:28:25]`.
> - Changed SQLite3 version string in `service.sh` description and notification message.
> - Changed root detection in `service.sh` to read persistent `.method` files for KernelSU and Magisk, with fallback version extraction.
> - Changed unknown values to `?` in APatch version handling for consistency.
---

> [3.51.0] - `2025-11-04`
>
> - Added dynamic SQLite version retrieval to display actual installed version in module description.
> - Added persistent `.method` file writing for all root methods (Magisk, APatch, KernelSU).
> - Added `architecture_check` function in `customize.sh` to print device architecture.
> - Added 15 devil-themed message variants in `customize.sh`.
> - Added default `TMPDIR=/data/local/tmp` and `trap` for automatic cleanup in `verify.sh`.
> - Added multi-algorithm hash support (`sha512`, `sha384`, `sha256`, `sha1`) with automatic fallback in `verify.sh`.
> - Changed root detection in `customize.sh` to separate functions per root method with variant identification.
> - Changed APatch version handling with GitHub API for KernelPatch tag.
> - Changed `android_version_check` in `customize.sh` with SDK codenames and architecture display.
> - Changed `extract_files` in `customize.sh` to include all binary architectures from ZIP.
> - Changed `verify_module` in `customize.sh` to extract and verify `module.prop` using `extract` function.
> - Removed initial command checks (`unzip`, `sha256sum`, etc.) in `verify.sh`.
---

> [3.50.4] - `2025-07-30`
>
> - Added `print_random_devil_message` and `post_install_actions` in `customize.sh` for modularized message and post-install logic.
> - Added `installisasi` function in `customize.sh` to streamline SQLite3 binary extraction.
> - Changed SQLite3 version to `3.50.4 [2025-07-30 19:33:53]`.
> - Changed notification in `customize.sh` to include reboot reminder.
> - Changed notification in `service.sh` to include SQLite version for clarity.
> - Changed `module.prop` description in `service.sh` by removing square brackets.
> - Removed icon from `service.sh` notification.
---

> [3.50.3] - `2025-07-17`
>
> - Added module banner for `KernelSU Next`.
> - Changed SQLite3 version to `3.50.3 [2025-07-17 13:25:10]`.
> - Changed `customize.sh` code improvements.
> - Changed `README.md` to be more professional and understandable.
---

> [3.50.2] - `2025-06-28`
>
> - Changed SQLite3 version to `3.50.2 [2025-06-28]`.
---

> [3.50.1] - `2025-06-06`
>
> - Changed SQLite3 version to `3.50.1 [2025-06-06]`.
> - Changed `update-binary` to be more optimal.
---

> [3.49.1] - `2025-02-18`
>
> - Added `verify.sh` to automate the integrity check.
> - Added `i386`, `armv8l`, and `armeabi` architecture support.
> - Added `service.sh` to update `module.prop`.
> - Changed `customize` and `functions` for all future modules.
> - Changed `LICENSE`, `README.md`, and added `CHANGELOG.md`.
---

> [3.49.0] - `2025-02-06`
>
> - Initial release.
---