"""Buck build file for the rust-select-os binary target.

This module defines a rust binary target that selects different source files
based on the target operating system platform.
"""

CRATE_ROOTS = {
    "prelude//os:linux": "src/main-linux.rs",
    "prelude//os:windows": "src/main-windows.rs",
    "prelude//os:macos": "src/main-mac.rs",
    "DEFAULT": "src/main.rs",
}

rust_binary(
    name = "select-os",
    srcs = select({
        "ovr_config//os:linux": ["src/main-linux.rs"],
        "ovr_config//os:windows": ["src/main-windows.rs"],
        "ovr_config//os:macos": ["src/main-mac.rs"],
        "DEFAULT": ["src/main.rs"],
    }),
    crate_root = select(CRATE_ROOTS),
    features = [],
)
