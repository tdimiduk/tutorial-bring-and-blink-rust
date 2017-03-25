# Linux

Here are the installation commands for a few Linux distributions.

## REQUIRED packages

- Ubuntu 16.04 or newer / Debian Jessie or newer:

```
$ sudo apt-get install \
  gcc-arm-none-eabi \
  gdb-arm-none-eabi \
  git \
  openocd
```

- Fedora 23 or newer:

```
$ sudo dnf install \
  arm-none-eabi-gcc-cs \
  arm-none-eabi-gdb \
  git \
  openocd
```

- Arch Linux

```
$ sudo pacman -S \
  arm-none-eabi-gcc \
  arm-none-eabi-gdb \
  git \
  openocd
```

## udev rules

These rules let you use USB devices like the STM32F3's built in JTAG debugger
without root privilege, i.e. `sudo`. To do this create the following file in
`/etc/udev/rules.d`:

```
$ cat >/etc/udev/rules.d/99-openocd.rules << EOL
# STM32F3DISCOVERY rev A/B - ST-LINK/V2
ATTRS{idVendor}=="0483", ATTRS{idProduct}=="3748", GROUP="uucp"

# STM32F3DISCOVERY rev C+ - ST-LINK/V2-1
ATTRS{idVendor}=="0483", ATTRS{idProduct}=="374b", GROUP="uucp"
EOL
```

Now check the results:

``
$ cat /etc/udev/rules.d/99-openocd.rules
# STM32F3DISCOVERY rev A/B - ST-LINK/V2
ATTRS{idVendor}=="0483", ATTRS{idProduct}=="3748", GROUP="uucp"

# STM32F3DISCOVERY rev C+ - ST-LINK/V2-1
ATTRS{idVendor}=="0483", ATTRS{idProduct}=="374b", GROUP="uucp"
```

Then reload the udev rules with:

```
$ sudo udevadm control --reload-rules
```

If you had the STM32F3NUCLEO plugged to your laptop, unplug it and then plug
plug it back in.

Finally, check if you are in the `uucp` group (or on Fedora the `dialout`
group).

```
$ groups $(id -nu)
(..) uucp (..)
     ^^^^
```

(`$(id -nu)` returns your user name. In my case it's `cwoodall`.)

If `uucp` (or `dialout`) appears in the output. You are all set! Go to the
[next section]. Otherwise, keep reading:

[next section]: 03-setup/verify.html

- Add yourself to the `uucp` (or `dialout`) group.

```
$ sudo usermod -a -G uucp $(id -u -n)
```

If you get:

```
usermod: group 'uucp' does not exist
```

Try to join the `dialout` group instead:

```
$ sudo usermod -a -G dialout $(id -u -n)
```


- Check again the output of `groups`. `uucp` (or `dialout`) should be there this
  time!

```
$ groups $(id -nu)
(..) uucp (..)
     ^^^^
```

You'll have to re-log for these changes to take effect. You have two options:

You can reboot or log out from your current session and then log in; this will
close all the programs you have open right now.

The other option is to use the command below:

```
$ su - $(id -nu)
```

to re-log *only in the current shell* and get access to `uucp` devices *only on
that shell*. Other shells *won't* have access to `uucp` devices unless you
manually re-log on them with the same `su` command.

Now, go to the [next section].
