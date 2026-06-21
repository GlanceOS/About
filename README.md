# 🌊 GlanceOS — OneUI 8 For PCs and Laptops 🚀

An ambitious, independent project aimed at porting Samsung's OneUI ecosystem and framework directly onto native x86_64 PC hardware. Built from the ground up on pure AOSP, completely decoupled from standard Android-x86 distributions.

---

## 🎯 The Vision

While standard Android distributions for PC focus on clone-like desktop interfaces, **GlanceOS** bridges the gap between Samsung’s premium ecosystem and standard desktop computers. We are extracting the core Framework, SystemUI, and application suite from modern Galaxy Tab architectures and transplanting them into a clean, optimized PC environment.

> ⚠️ **Status:** Active Development / Experimental Phase.

---

## ✨ Key Features (Under Development)

*   **Pure Core Foundation:** Built directly on pure AOSP x86_64 architecture for lightweight and independent performance.
*   **One UI Home Integration:** Full desktop-native layout featuring the Galaxy Tablet dock, app drawer blur animations, and responsive split-screen viewports.
*   **Samsung DeX Capabilities:** Unlocking native Desktop Mode on PC hardware, allowing a full multi-window workstation experience.
*   **SystemUI Transplant:** Replaced standard AOSP status bars with the iconic rounded, fluent OneUI Control Center and quick settings.
*   **ARM-to-x86 Translation Layer:** Native integration of translation bridges (`libhoudini` / `libndk`) to allow proprietary Samsung apps to execute flawlessly on Intel and AMD processors.

---

## 🛠️ Installation Steps (Experimental)

Since GlanceOS is built as a native standalone live image, you can flash it and run it directly from a USB drive without touching your main hard drive.

1.  **Prepare your USB Drive:** Plug in a USB flash drive (Minimum 4GB - 8GB recommended).
2.  **Download the Tool:** Open **Rufus** (latest version).
3.  **Select the Image:** Choose the target GlanceOS `.iso` image in Rufus.
4.  **Configure Partition Scheme:**
    *   Select **MBR** if you are targeting older BIOS systems.
    *   Select **GPT** if you are targeting modern UEFI systems.
5.  **Flash in DD Mode (Crucial):** Click *Start*. When prompted by Rufus, make sure to select **Write in DD Image mode**. Android-x86 based structures require DD mode to properly construct the boot sectors.
6.  **Boot:** Restart your PC, press your motherboard's Boot Menu key (F12, F11, F8, or Esc), and select your USB drive. Choose **"Run GlanceOS without installation"** to test it live!

---

## 🐛 Known Bugs & Workarounds (Alpha Stage)

As we are manually transplanting the Samsung framework into a pure x86_64 environment, expect heavy instability in this alpha phase.

*   **Samsung Account Sign-in:** `CRITICAL` — Currently bootloops or crashes. The system searches for Samsung Knox components and security chips which do not exist on standard PC hardware. 
    *   *Workaround:* Skip Samsung Account setup during the first boot wizard.
*   **Hardware Acceleration (GPU):** `MEDIUM` — Some OneUI blur animations (like the app drawer background) might lag or cause visual artifacts on older Intel HD Graphics or Nvidia cards due to GLES translation layers.
*   **Audio Routing:** `LOW` — Sound might not automatically switch when plugging in HDMI or external audio jacks.
*   **DeX Mode Resolution:** `MEDIUM` — When launching Samsung DeX on certain ultrawide monitors, the UI scaling might distort. 
    *   *Workaround:* Force standard 16:9 or 16:10 resolutions in the display options.
