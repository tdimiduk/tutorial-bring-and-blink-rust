# Setting up your development environment

This section describes the common steps needed to set up rust and supporting tools. Before following this section you should follow the OS specific sections:

- [Linux]
- [macOS]
- [Windows]

[Linux]: 03-setup/linux.html
[macOS]: 03-setup/macos.html
[Windows]: 03-setup/windows.html

## Requirements

We will use the following programs and tools. Where a minimum version is not
specified, any recent version should work but we have listed the version we have
tested.

1. cargo & `rustc` (>= rust nightly 1.14).
2. [Xargo] >= 0.2.x.
3. [`itmdump`] >= 0.1.1
4. OpenOCD >=0.8. Tested version: 0.9.0
5. An `arm-none-eabi-gcc` toolchain. Including:
  - `arm-none-eabi-gcc`. Tested versions: 4.8, 5.2 and 6.2
  - `arm-none-eabi-gdb`. Version 7.12 or newer highly recommended. Tested versions: 7.10, 7.11 and 7.12

[Xargo]: https://crates.io/crates/xargo
[`itmdump`]: https://crates.io/crates/itm

Next, follow OS-agnostic installation instructions for a few of the tools:

### `rustc` & Cargo

The preferred way to install rust and cargo is to follow the instructions
at https://www.rust-lang.org/ for your particular platform. You should use
the instructions which install `rustup`. Afterwards we will need to download
and install the `nightly` build which is required for embedded development
for the time being. To do that:

```
$ rustup default nightly
$ rustup component add rust-src # for Xargo later.
```

### Xargo

You can install Xargo in two different ways:

- By grabbing a [binary release] and placing it somewhere in your `$PATH`.
  `$HOME/.cargo/bin` is a good place to install it to. Do make sure that the
  binary release you "installed" actually works by executing the following
  command:

```
$ xargo -V
xargo 0.2.0 (bd8ebc4 2016-10-16)
cargo 0.13.0-nightly (a8baa5b 2016-10-15)
```

[binary release]: https://github.com/japaric/xargo/releases

- Or, by building it yourself with the following command:

```
$ cargo install xargo
$ xargo -V
```

### `itmdump`

```
$ cargo install itm
```

### OS specific instructions

If you have not followed the platorm specific instructions please follow them
now:

- [Linux](03-setup/linux.html)
- [Windows](03-setup/windows.html)
- [macOS](03-setup/macos.html)
