# Knowledge Requirements

The main "knowledge requirement" for following along with this tutorial is to
know some Rust. To get "some" knowledge I recommend walking through the
[`Guessing Game` tutorial](https://doc.rust-lang.org/book/guessing-game.html)
and reading through some of the official [The Rust Programming Language Book].
This should give you a sufficient base of knowledge.

[The Rust Programming Language Book]: https://doc.rust-lang.org/book

# Hardware Requirements

Here are the materials we will be using:

- A [STM32 NUCLEO-F303RE] development board. Which is a simple, but powerful
  Arduino-compatible development board.

[STM32 NUCLEO-F303RE]: http://www.st.com/en/evaluation-tools/nucleo-f303re.html
  - You can purchase this board from [Mouser][0] or [Digikey][1].

[0]: http://www.mouser.com/ProductDetail/STMicroelectronics/NUCLEO-F303RE/?qs=%2fha2pyFaduhMljemrTB2TiWNA%252b8NWaDxaSD%252bvQZGxBvfwZmOimB6MjCEAFnAFVgy
[1]: https://www.digikey.com/products/en?keywords=NUCLEO-F303RE

<p align="center">
![STM32 NUCLEO-F303RE](assets/f3.jpg)
</p>

- One mini-B USB cables. One is required to make the STM32 NUCLEO board
  work.

<p align="center">
<img title="mini-B USB cable" src="assets/usb-cable.jpg">
</p>

> **NOTE** These are **not** the USB cables that ship with pretty much every
> Android phone; those are *micro* USB cables. Make sure you have the right
> thing!

- OPTIONAL. Bring some shields, LEDS, and wires to play around with!

> **FAQ**: Wait, why do I need this specific hardware?

It makes my life and yours much easier.

The material is much, much more approachable if we don't have to worry about
hardware differences. Trust me on this one.

> **FAQ**: Can I follow this material with a different development board?

Maybe? It depends mainly on two things: your previous experience with
microcontrollers and/or whether there already exists a high level crate, like
the [f3], for your development board somewhere.

Regardless, with a different development board, this text would lost most if not
all its beginner friendliness and "easy to follow"-ness, IMO.

If you have a different development board and you don't consider yourself a
total beginner, you are better off reading the [Copper] book which approaches
the Rust on microcontrollers topic in a bottom-up and device agnostic way. Or,
maybe even just read the source of the [f3] crate.

[Copper]: https://japaric.github.io/copper
[f3]: https://github.com/japaric/f3
