---
title: "Remote Access with WireGuard"
date: 2026-03-31
type: "page"
draft: false
---

# Remote Access Guide

Most of the **Two Secret Weapons** apps like **AxeWatch**, **Prologue**, and **LabPing** are designed to communicate directly with devices on your local home network (LAN). To access your Bitaxe miners, Audiobookshelf server, or homelab nodes when you are away from home, we recommend setting up a **Virtual Private Network (VPN)** using **WireGuard**.

Using a VPN is the most secure way to access your devices without exposing them directly to the open internet.

---

### 1. Download the App
First, you need the WireGuard client on your Android device. It is open-source and free.

* **Google Play Store:** [WireGuard for Android](https://play.google.com/store/apps/details?id=com.wireguard.android)
* **F-Droid:** [WireGuard on F-Droid](https://f-droid.org/en/packages/com.wireguard.android/)
* **Direct APK:** [WireGuard GitHub Releases](https://github.com/WireGuard/wireguard-android/releases)

---

### 2. Setting Up Your Server
Before the app can connect, you need a WireGuard "Server" (Peer) running at your home. There are several ways to do this depending on your technical comfort level:

| Method | Best For | Guide Link |
| :--- | :--- | :--- |
| **PiVPN** | Raspberry Pi / Linux users | [pivpn.io](https://www.pivpn.io/) |
| **Home Assistant** | Users with an existing HA setup | [WireGuard Add-on Guide](https://github.com/hassio-addons/addon-wireguard/blob/main/wireguard/DOCS.md) |
| **Tailscale** | Easiest setup (No port forwarding) | [Tailscale Android Guide](https://tailscale.com/kb/1017/install-android/) |
| **Router-Based** | TP-Link, ASUS, or OpenWRT routers | *Check your router admin panel* |

---

### 3. How to Connect Your Phone
Once your server is configured, adding it to your Android phone is designed to be as simple as possible.

#### Option A: The QR Code (Easiest)
1.  On your server/computer, generate a **Client Config QR Code**.
2.  Open the WireGuard app on Android.
3.  Tap the **(+)** icon in the bottom right.
4.  Select **Scan from QR code**.
5.  Point your camera at the screen. Give the tunnel a name (e.g., "Home") and save it.

#### Option B: Importing a File
1.  Transfer the `.conf` file from your server to your phone (via USB, ProtonDrive, or local transfer).
2.  Open the WireGuard app.
3.  Tap the **(+)** icon and select **Import from file or archive**.
4.  Select your `.conf` file.

---

### 4. Using the Apps Remotely
Once the WireGuard toggle is switched **ON** in the Android app:

1.  Your phone acts as if it is sitting on your home Wi-Fi.
2.  Open **AxeWatch** or **LabPing**.
3.  Use the **local IP addresses** (e.g., `192.168.1.50`) just as you would when sitting at home.
4.  **Note:** Ensure your "Allowed IPs" in the WireGuard config includes your home subnet (usually `192.168.1.0/24`) so the app knows which traffic to send through the tunnel.

---

### 5. Troubleshooting
* **Can't connect?** Ensure you have forwarded the WireGuard port (usually UDP `51820`) on your home router to your server's IP.
* **No Internet?** If you can see your miners but can't browse the web, check your "DNS" settings in the WireGuard app config (setting it to `1.1.1.1` or your local Pi-hole IP usually fixes this).