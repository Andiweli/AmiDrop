# AmiDrop – File Transfer for AmigaOS

![AmigaOS](https://img.shields.io/badge/AmigaOS-3.0%2B-orange)
![AI](https://img.shields.io/badge/AI-assisted%20coding-6e7781)

[![Join The Lair on Discord](https://img.shields.io/badge/Discord-The%20Lair-5865F2?logo=discord&logoColor=white)](https://discord.gg/AB3WVBqD5G)
[![Support via PayPal](https://img.shields.io/badge/Support%20via-PayPal-0070BA?logo=paypal&logoColor=white)](https://paypal.me/andiweli)

AmiDrop is a lightweight native **AmigaOS file transfer utility** for sending files from smartphones, PCs and other devices directly to an Amiga through a **web browser**. No companion app is required.

<img width="500" height="368" alt="image" src="https://github.com/user-attachments/assets/ea6aae57-6970-4a40-8d12-f8584268a571" />

## ✨ Features

- Browser-based file transfer to AmigaOS
- QR code for quick connection from phones and tablets
- 6-digit pairing code for PCs and other devices
- Direct streaming to disk with safe temporary files
- Configurable receive folder and file size limit
- Two interchangeable interfaces: **GadTools** for classic Amiga screen
  modes, and **MUI**

## 🖥️ Requirements

- **AmigaOS 3.0 or newer**
- TCP/IP stack providing `bsdsocket.library`
- Network connection between the Amiga and sending device

Each interface adds its own requirement:

| Program | Needs |
|---|---|
| `AmiDrop` | nothing beyond the above (GadTools is part of AmigaOS) |
| `AmiDrop_MUI` | MUI 3.8 (`muimaster.library` 19) or newer |

AmiDrop works with common Amiga TCP/IP stacks such as Roadshow, AmiTCP and Miami.

## 🔨 Building

Cross-compiled with Bebbo's `m68k-amigaos-gcc`. The frontend is selected at
build time; the network, upload and QR code parts are shared.

```
make                 # AmiDrop           - GadTools (default)
make GUI=mui         # AmiDrop_MUI       - MUI 3.8 or newer
make host-test       # unit tests, compiled and run on the build host
```

There is a third target, `make GUI=reaction`. It builds the unfinished
ReAction sources that came with the original project; they are not released,
not documented and have not been run, so treat that target as a developer
convenience rather than a version of the program.

The MUI build needs the MUI developer headers. Point `MUI_INCLUDE` at them if
they are not in the default location:

```
make GUI=mui MUI_INCLUDE=/path/to/MUI/C/include
```

## 🚀 Usage

1. Start AmiDrop on the Amiga.
2. Scan the displayed QR code or enter the shown address in a browser.
3. Select a file and upload it directly to the configured receive folder.

No software needs to be installed on the sending device.

## ❤️ Support

If you enjoy this project and would like to support my work, you can make a small contribution via PayPal.

Your support helps me spend more time maintaining existing projects, fixing bugs, improving compatibility, and working on new features.

[![Support via PayPal](https://img.shields.io/badge/Support%20via-PayPal-0070BA?logo=paypal&logoColor=white)](https://paypal.me/andiweli)

[![Join The Lair on Discord](https://img.shields.io/badge/Discord-The%20Lair-5865F2?logo=discord&logoColor=white)](https://discord.gg/AB3WVBqD5G)

Thank you for your support!

## ⚖️ Credits

AmiDrop © 2026 Andreas "Andiweli" Stürmer.

MUI edition by Jan Zahurancik / AmiKit.

QR code generation is based on work by Richard Moore / Project Nayuki.
