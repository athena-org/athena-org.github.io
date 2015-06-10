---
layout: page
title: "Build Environment"
category: start
date: 2015-06-10 10:05:34
---

Before working with any of the Athena tools, you will need to set up your build environment.
What you will need will depend on if you want to use or work on the Athena tools.


## Rust

Athena is built on Rust, a fast and safe systems programming language. Some Athena tools need
to compile Rust code at runtime, so you will need to install the Rust compiler. Since all Athena
projects are written in Rust as well, you will need the compiler when you work on them.

You can install Rust by going to the [Rust download page](http://www.rust-lang.org/install.html)
and installing **Rust Nightly 32 bit**. Currently, not all projects will work on stable or 64 bit.


## Native Dependencies (Development Only)

If you want to work on Athena tools rather than just use them, you will need to have the native
dependencies needed to build them installed. **Currently you also need to do this manually if
you want to use phosphorus.**

Download the Windows *libfreetype-6.dll* and *zlib1.dll* from the [freetype site](http://www.freetype.org/download.html).
Put these two DLLs together in a folder where you wan to keep your dependencies.

In the Rust project you want to set up the native dependencies for, create a new folder ".cargo".
In this new folder, create a file "config" with the following content:

```toml
[target.i686-pc-windows-gnu.freetype]
rustc-link-search = ["C:/PATH/TO/DEPENDENCIES"]
rustc-link-lib = ["freetype-6"]
root = "C:/PATH/TO/DEPENDENCIES"
```
