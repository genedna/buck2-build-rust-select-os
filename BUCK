load("@prelude//toolchains:rust.bzl", "system_rust_toolchain")

CRATE_ROOTS = {
    "ovr_config//os:linux": "src/main-linux.rs",
    "ovr_config//os:windows": "src/main-windows.rs",
    "ovr_config//os:macos": "src/main-mac.rs",
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
