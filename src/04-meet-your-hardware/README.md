# Meet your hardware

Let's get familiar with the hardware we'll be working with.

## STM32F3DISCOVERY (the "F3")

<p align="center">
<img title="F3" src="assets/f3.jpg">
</p>

We'll refer to this board as "F3" throughout this book.

What does this board contain?

- A STM32F303VCT6 microcontroller. This microcontroller has
  - A single core ARM Cortex-M4F processor with hardware support for single
    precision floating point operations and a maximum clock frequency of 72 MHz.

  - 256 KiB of "Flash" memory. (1 KiB = 10**24** bytes)

  - 48 KiB of RAM.

  - many "peripherals": timers, GPIO, I2C, SPI, USART, etc.

  - lots of "pins" that are exposed in the two lateral "headers".

  - **IMPORTANT** This microcontroller operates at (around) 3.3V.

- An [accelerometer] and a [magnetometer][] (in a single package).

[accelerometer]: https://en.wikipedia.org/wiki/Accelerometer
[magnetometer]: https://en.wikipedia.org/wiki/Magnetometer

- A [gyroscope].

[gyroscope]: https://en.wikipedia.org/wiki/Gyroscope

- 8 user LEDs arranged in the shape of a compass

- A second microcontroller: a STM32F103CBT. This microcontroller is actually
  part of an on-board programmer and debugger named ST-LINK and is connected to
  the USB port named "USB ST-LINK".

- There's a second USB port, labeled "USB USER" that is connected to the main
  microcontroller, the STM32F303VCT6, and can be used in applications.

## Documentation

Tooling is not everything though. Without documentation it is pretty much
impossible to work with microcontrollers (unless you are very good at reverse
engineering and even then it would be a *lot* more work).

We'll be referring to all these documents throughout this book:

- [STM32F3DISCOVERY User Manual][um]
- [STM32F303VC Datasheet][ds]
- [STM32F303VC Reference Manual][rm]
- [LSM303DLHC]
- [L3GD20]

[L3GD20]: http://www.st.com/resource/en/datasheet/l3gd20.pdf
[LSM303DLHC]: http://www.st.com/resource/en/datasheet/lsm303dlhc.pdf
[ds]: http://www.st.com/resource/en/datasheet/stm32f303vc.pdf
[rm]: http://www.st.com/resource/en/reference_manual/dm00043574.pdf
[um]: http://www.st.com/resource/en/user_manual/dm00063382.pdf


## The Serial module

<p align="center">
<img title="Serial module" src="assets/serial.jpg">
</p>

We'll use this module to exchange data between the microcontroller in the F3 and
your laptop. This module will be connected to your laptop using an USB cable. I
won't say more at this point.

## The Bluetooth module

<p align="center">
<img title="The HC-05 Bluetooth module" src="assets/bluetooth.jpg">
</p>

This module has the exact same purpose as the serial module but it sends the
data over Bluetooth instead of over USB.
