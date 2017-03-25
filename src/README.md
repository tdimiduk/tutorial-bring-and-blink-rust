# Boston Embdded Systems Meetup: Bring and Blink

> Discover the world of microcontrollers through [Rust]!

[Rust]: https://www.rust-lang.org/en-US/

This book is an edited version for the Boston Embedded Systems Meetup and is
based on [japaric's `discovery` book](http://japaric.github.io/discovery).
This book is for an "introductory tutorial" on microcontroller-based "embedded
systems" that uses Rust as the teaching language rather than the usual C/C++.

## Scope

The following topics will be covered in this tutorial:

- How to write, build, flash and debug an "embedded" (Rust) program.

- How to make LEDs blink, print messages over JTAG using itm, and some basic
  Rust.

## Approach

- Beginner friendly. No previous experience with microcontrollers or embedded
  systems is required.

- Hands on. Plenty of exercises to put the theory into practice. *You* will be
  doing most of the work here.

- Tool centered. We'll make plenty use of tooling to ease development. "Real"
  debugging, GDB, and logging will be introduced early on. Using LEDs as a
  debugging mechanism has no place here.

## Non-goals

What's out of scope for this tutorial:

- Teaching Rust in depth. There is plenty of material, and the officia [Rust
  Programming Language Book](https://doc.rust-lang.org/book/) is a great place
  to start.

- Being a comprehensive introduction about electric circuit theory or
  electronics. We'll just cover the minimum required to understand how some
  devices work (if at all).

- Covering Rustic, low-level details. We won't be talking about linker scripts,
  the boot process or how to glue those two into a minimally working Rust
  program. The [Copper] book has information on those topics though.

- Working with peripherals or anything more complicated than LEDs and basic
  Rust programs the [Discovery] book is a great place to go after this book and
  will keep you going. (Thanks japaric!)

- Being a general reference for programming microcontrollers. The intent is to
  get a handful of people up and running in a short period of time! Depth is
  not our aim!

[Copper]: https://japaric.github.io/copper/
[Discovery]: https://japaric.github.io/discovery/

## Thanks To:

- Canopy: for allowing us to use their space.
- japaric: for writing a majority of the content.

### Original Sponsors of the Discovery book

This tutorial is based on japric's Discovery book which was sponsored by:

<p align="center">
<a href="http://integer32.com/">
<img style="width: 50%" title="integer 32" src="assets/integer32.svg">
</a>
</p>

Many thanks to [integer 32](http://integer32.com/) for sponsoring me to continue
working on this book! Please give them lots of work (they do Rust consulting!)
so they'll have no choice but to hire more Rustaceans <3.
