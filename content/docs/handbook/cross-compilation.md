---
title: "Cross-compilation"
draft: false
---

Kreato Linux, and its package manager `kpkg` supports cross-compilation. 

Cross-compilation allows you to build packages for another architecture/system without the use of emulation.

## Gathering a cross-compiler
Cross-compilation requires a cross-compilation toolchain to build packages with. Kreato Linux currently has `aarch64-linux-gnu` cross-compiler toolchain available on the repositories at moment, additions are welcome.

You can install the binary first, then build later, or just install the binary and use that. Kreato Linux also provides the `builder-aarch64-cross-gnu` container that has a toolchain setup by default. Please note that cross-compilation without having a binary first will not be possible, as building `glibc` and `libxcrypt` requires a cross-compiler to be present, creating a circular dependency.

## Cross-compiling Kreato Linux packages
Now that you have a cross-compiler toolchain, you can build packages by running `kpkg build packageName --target=target`. Replace `target` with the desired target, such as `aarch64-linux-gnu`. If the package is supported, it should build (and install if `--dontInstall` is not used) the package with the specified target.


