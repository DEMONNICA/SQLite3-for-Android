> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.51.0] `2025-11-04`
>
> - Updated SQLite binary version from 3.50.4 (2025-07-30) to 3.51.0 (2025-11-04) in `service.sh` description and notification message.
> - Enhanced APatch detection in `service.sh` and `customize.sh` with detailed version fetching: VAPK from `dumpsys package`, VKER from GitHub API `curl`, and storage in `/data/adb/ap/kernelver` for consistent `ROOT_VERSION` formatting.
> - Reordered Magisk `ROOT_VERSION` to `"${MAGISK_VER_NAME} ${MAGISK_VER_CODE}"` for better readability in `service.sh`.
> - Added fallback `"Unknown"` for `ANDROID_VERSION` and `ANDROID_SDK` using `|| echo` in `service.sh`.
> - Compressed emoji `case` statement into a single line with `;;` separators in `service.sh` for conciseness.
> - Added `-S bigtext` to `cmd notification post` in `service.sh` for improved display.
> - Improved `root_detect` in `customize.sh` with dynamic APatch kernel version retrieval via GitHub API and file persistence.
> - Simplified `module_remove_check` in `customize.sh` by removing `ui_print` logs and directly aborting on failure for cleaner error handling.
> - Enhanced `android_version_check` in `customize.sh` with SDK codenames (Q, R, S, etc.) and added architecture display using `ARCH=$(uname -m)`.
> - Added `architecture_check` function in `customize.sh` to print device architecture.
> - Expanded `extract_files` in `customize.sh` to include all binary architectures (`aarch64`, `armv7a`, `x86_64`, `x86`) from ZIP.
> - Increased random devil-themed messages to 15 variants in `print_random_devil_message` for more variety.
> - Integrated `verify_module` in `customize.sh` to extract and verify `module.prop` using the `extract` function.
> - Added default `TMPDIR=/data/local/tmp` and `trap` for automatic cleanup of `TMPDIR_FOR_VERIFY` on exit in `verify.sh`.
> - Enhanced `verify.sh` `extract` function with multi-algorithm hash support (`sha512`, `sha384`, `sha256`, `sha224`, `sha1`) and automatic fallback to the first available.
> - Included `actual_hash` in checksum mismatch error message in `verify.sh` for better debugging.
> - Removed initial command checks (`unzip`, `sha256sum`, etc.) in `verify.sh` as they are assumed available.
> - General code cleanup: improved indentation, removed redundant variables, enhanced error handling, and ensured broader compatibility across root methods and architectures.
---