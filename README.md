<p align="center">
  <img src="https://user-images.githubusercontent.com/234234/logo-placeholder.png" alt="Redmi SE Logo" height="120"/>
</p>

<h1 align="center">🚀 Redmi Pad SE – MIUI Debloat Guide by Afiq</h1>

<p align="center">
  Remove Xiaomi bloatware, boost performance, and clean up your tablet like a pro.<br>
  No root needed. Pure ADB and clean execution.
</p>

---

## ✅ Requirements

- Windows PC
- USB Cable (data-capable)
- Universal Android Debloater (UAD)
- ADB Platform Tools

---

## 📥 Downloads

### 🔧 ADB Platform Tools:
👉 [Download ADB](https://developer.android.com/tools/releases/platform-tools)

- Extract the ZIP to a folder (e.g., `C:\adb\platform-tools`)

### 🔧 Universal Android Debloater (UAD):
👉 [Download UAD](https://github.com/0x192/universal-android-debloater/releases)

- Download `uad_gui-windows.exe`
- No installation needed

---

## ⚙️ Environment Setup (Windows)

To run `adb` globally from Command Prompt:

1. Copy your ADB path (e.g. `C:\adb\platform-tools`)
2. Open **Environment Variables** → Edit `Path` under System Variables
3. Add new entry: your ADB path
4. Test with:
```bash
adb version
```

---

## 📱 Enable Developer Mode

1. `Settings > About tablet` → Tap **MIUI Version** 7x
2. Go to `Developer Options`:
   - Enable: **USB Debugging**, **Install via USB**, *(Optional: Security Debugging)*
3. Connect tablet via USB
4. Approve debug prompt

---

## 🧼 Debloat Script

Create a file named `afiq_debloat.bat` in `platform-tools` and paste:

```bat
@echo off
echo === Afiq's Redmi SE Debloat Script ===

REM --- System Bloat ---
adb shell pm uninstall --user 0 com.miui.huanji
adb shell pm uninstall --user 0 com.miui.securitycenter
adb shell pm uninstall --user 0 com.miui.guardprovider
adb shell pm uninstall --user 0 com.miui.securityadd

REM --- Disabled System-Locked Apps ---
adb shell pm disable-user --user 0 com.xiaomi.scanner
adb shell pm disable-user --user 0 com.miui.screenrecorder
adb shell pm disable-user --user 0 com.miui.weather2
adb shell pm disable-user --user 0 com.miui.creation
adb shell pm disable-user --user 0 com.miui.mediaeditor

REM --- Optional Apps ---
adb shell pm uninstall --user 0 com.xiaomi.calendar
adb shell pm uninstall --user 0 com.duokan.phone.remotecontroller

echo === Debloat complete! Enjoy your clean tablet 😎 ===
pause
```

---

## 🔄 Restore (Reinstall a Package)

```bash
adb shell cmd package install-existing com.package.name
```

Example:
```bash
adb shell cmd package install-existing com.miui.weather2
```

---

## ✅ Result

- 🚫 No ads or system nags
- ⚡ Faster performance, less RAM usage
- ✨ Close to stock Android experience

---

<p align="center">
  Built with 💻 + 😤 + ☕ by Afiq
</p>
