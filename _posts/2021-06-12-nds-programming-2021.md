---
layout: post
title: "🇬🇧 How to develop Nintendo DS games in 2021"
published: true
---

![Nintendo DS](../img/nds/nds.jpg)

Before starting to code for our beloved Nintendo DS, we need some tools, like the right compiler (kindly provided by [devkitPro](https://devkitpro.org/)) and the right libraries.

## Step 1. Download and install devkitPro pacman

First of all we need to download the devkitPro package manager. We will use it to download the devkitARM toolchain and Nintendo DS libraries.

- Linux: use this guide: [https://devkitpro.org/wiki/devkitPro_pacman](https://devkitpro.org/wiki/devkitPro_pacman)
- Windows: [https://github.com/devkitPro/installer/releases](https://github.com/devkitPro/installer/releases) ← take the latest version
- OSX: use the installer [https://github.com/devkitPro/pacman/releases](https://github.com/devkitPro/pacman/releases) ← take the latest version

After you installed pacman, you'll need to set up the following environment variables:

```bash
DEVKITPRO=/opt/devkitpro
DEVKITARM=$DEVKITPRO/devkitARM
PATH=$PATH:$DEVKITARM/bin
```

*If you don't know how to do it, just google* `how to set environment variables on <your OS>`.

## Step 2. Install devkitARM and NDS libraries

It's time to open your terminal! Move to `/opt/devkitpro/pacman/bin`.

```bash
cd /opt/devkitpro/pacman/bin
```

This command will do all the work:

```bash
./pacman -Sl nds-dev
```

## Step 3. Emulate!

It's time to download an emulator, if you don't already have one. My personal suggestion is [melonDS](http://melonds.kuribo64.net/downloads.php), it's a very complete emulator, with lots of settings and even some Wifi functions work on it.

## Step 4. Compile!

Luckly, in step 4 we installed a bunch of code examples together with the libraries. For making sure that everything works well, let's start with the `hello_world` example.

Now move into `/opt/devkitpro/examples/nds/hello_world` with your terminal.

```bash
cd  /opt/devkitpro/examples/nds/hello_world
```

You can rather work directly in this directory, or copy it somwhere else.

Let's compile, type the following command:

```bash
make
```

If you get an error like `Permission denied`, type this:

```bash
cd ..
sudo chmod 777 hello_world
cd hello_world
make
```

## Set 4. Run!

Now, if everything went well, in your `hello_world` directory there's a `hello_world.nds` file. Open this with your emulator, and you're done!

![Hello world](../img/nds/hello_world.jpg)

## Step 5. Have fun!

Now you can code your personal Nintendo DS game. Here's the documentation of `libnds`, it will be useful: [https://libnds.devkitpro.org/](https://libnds.devkitpro.org/).

## Issues

If you encountered problems following this guide (especially during step 1 on windows) you can refer to this guide: [https://devkitpro.org/wiki/devkitPro_pacman](https://devkitpro.org/wiki/devkitPro_pacman)

Otherwise just send me an e-mail at `salvatore@giammanco.me`, and i will try my best to help you.

## Buy me a beer

If you enjoyed the article, and wish to buy me a beer, tip me at the following `bitcoin` address: `3CG6P8mpfk5d5DZ9psVDBesyAii3BC5pkS`.

If you don't use bitcoin yet, you can tip me here: [https://www.buymeacoffee.com/firec00l](https://www.buymeacoffee.com/firec00l)