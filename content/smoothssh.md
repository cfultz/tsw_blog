---
title: "SmoothSSH"
description: "A high-performance, gesture-driven SSH client for Android built for sysadmins."
type: "page"
---

# SmoothSSH: Terminal Velocity

**SmoothSSH** is a high-performance, gesture-driven SSH client for Android, built specifically for sysadmins who need speed, security, and a frictionless terminal experience on the move.

Forget clunky menus and dropped frames. SmoothSSH provides a smooth interface optimized for modern hardware, ensuring 60fps terminal scrolling and cryptographic handshakes that don't hang your UI.

### ✨ Key Features

* **Multi-Session Swiping:** Fluidly swipe left or right on the terminal canvas to instantly snap between active SSH sessions across your cluster.
* **The Transcript Engine:** One tap dumps your entire live terminal buffer into a native, searchable text view—perfect for grabbing IP addresses or logs.
* **Dynamic Control Row:** A mobile-optimized accessory row that seamlessly swaps to vital keys (SIGINT, EOF, SUSPEND) the moment you tap CTRL.
* **Encrypted Vault:** All connections and private keys are stored in a heavily encrypted local vault using **AES-256**.
* **Biometric App Lock:** Secure the entire application behind your device's native Fingerprint, Face ID, or PIN.
* **Volume Rocker Scaling:** Instantly scale your terminal font size up or down using your phone's physical volume buttons.

### 🛠️ Performance Stack

SmoothSSH is built on a lean, AOT-compiled stack to ensure maximum security and rendering speed:

* **Terminal Emulator:** `xterm.dart`
* **SSH/Crypto:** `dartssh2` (Native Compiled)
* **Security:** `flutter_secure_storage` & `local_auth`
* **UI Engine:** Flutter (Custom Cupertino Slide Transitions)

---

### 🚀 Get Started

SmoothSSH is open-source and built for the community. You can compile it yourself or grab the latest automated build.

**Installation via CLI:**
```bash
git clone https://github.com/cfultz/smoothssh.git
cd smoothssh
flutter pub get
flutter run --release