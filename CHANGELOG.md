> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.51.3] - `2026-03-13`
>
> - License Changes.
> - Changed the structure of `README.md` for a better impression.
> - Updated `customize.sh` and `verify.sh` for better future performance.
> - Improved `customize.sh` ABI detection and file extraction based on architecture.
> - Added `Donate` action in module.
> - Added backup of original `/system/bin/sqlite3` before replacing.
> - Added automatic restore of original `sqlite3` on uninstall via `uninstall.sh`.
> - Added WAL checkpoint, VACUUM, ANALYZE, and integrity check on all system databases.
> - Added orphan WAL/SHM and uninstalled app database cleanup.
> - Added fstrim on `/data`, `/user`, and `/cache` after optimization.
> - Added system notification when optimization is complete.
> - Replaced `action.sh` with `optimize.sh` for post-reboot database optimization.
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