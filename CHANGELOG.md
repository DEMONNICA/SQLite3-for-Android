> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.53.0] - `2026-04-09`
>
> - SQLite3 version update `3.53.0 [2026-04-09 11:41:38]`
> - Fixed `optimize.sh` force-stop incorrectly targeting system packages causing volume lock bug.
> - Added system package exclusion — only third-party apps are force-stopped during optimization.
> - Fixed `MODDIR` in `uninstall.sh` to use `readlink -f` for correct path resolution.
> - Fixed typo `post_install_actions` → `post_install_action` in `customize.sh`.
> - Removed `SKIPUNZIP=1` and `DEBUG=false` from `customize.sh`.
> - Added backup confirmation message in `customize.sh`.
> - Updated banner image and SQLite version string in `README.md`.
---

> [3.51.3] - `2026-03-13`
>
> - License Changes.
> - Changed the structure of `README.md` for a better impression.
> - Updated `README.md` description and feature list.
> - Updated `customize.sh` and `verify.sh` for better future performance.
> - Improved `customize.sh` ABI detection and file extraction based on architecture.
> - Improved `detect_root_all` to match latest root manager variants.
> - Improved `set_donate_link` timezone detection with multiple fallbacks.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Added `FolkLite` (`mi.yuki.folk`) detection to `detect_root_all`.
> - Added backup of original `/system/bin/sqlite3` before replacing.
> - Added automatic restore of original `sqlite3` on uninstall via `uninstall.sh`.
> - Added numbered comments throughout `customize.sh` for better readability.
> - Replaced `action.sh` with `optimize.sh` for post-reboot database optimization.
> - Added WAL checkpoint, VACUUM, ANALYZE, and integrity check on all system databases.
> - Added orphan WAL/SHM and uninstalled app database cleanup.
> - Added fstrim on `/data`, `/user`, and `/cache` after optimization.
> - Added system notification when optimization is complete.
> - Updated `service.sh` to run `optimize.sh` via `setsid` after reboot.
> - Removed `action.sh`, replaced by `optimize.sh`.
---

> [3.51.2] `2026-01-09`
>
> - SQLite3 version update `3.51.2 [2026-01-09 17:27:48]`
> - Added `action.sh` to check for the latest version of `sqlite3`.
> - Code changes and improvements in `customize.sh`.
> - Code changes in `verify.sh` for stronger module security improvements.
> - Remove `notification` and some minor changes in `service.sh`.
> - And added the deletion code `(.method)` in `uninstall.sh`.
---