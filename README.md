# VB6 IDE Mouse Wheel Fix

A re-hosted copy of Microsoft's discontinued Visual Basic 6 IDE Mouse Wheel Add-In.

## Overview

Microsoft released an official add-in to add mouse wheel support to the Visual Basic 6.0 IDE. Unfortunately, the original download was removed from Microsoft's servers, making it increasingly difficult for developers maintaining legacy VB6 applications to obtain.

This repository preserves the original add-in and installation files so that VB6 developers can continue using mouse wheel scrolling within the VB6 code editor and related IDE windows.

## Features

- Adds mouse wheel scrolling support to the VB6 IDE
- Integrates as a standard VB6 Add-In
- Can be loaded automatically when VB6 starts
- Original Microsoft implementation

## Installation

### 32-bit and 64-bit Windows

1. Download or clone this repository.
2. Locate `VB6IDEMouseWheelAddin.dll`.
3. Open **Command Prompt** as **Administrator**.
4. Navigate to the folder containing the DLL.

Register the add-in:

```cmd
regsvr32 VB6IDEMouseWheelAddin.dll
```

You should receive a message stating that registration succeeded.

### Alternative Installation

Some users prefer copying the DLL to the Windows system folder before registering it.

#### 32-bit Windows

Copy:

```text
VB6IDEMouseWheelAddin.dll
```

to:

```text
C:\Windows\System32
```

Then run:

```cmd
regsvr32 C:\Windows\System32\VB6IDEMouseWheelAddin.dll
```

#### 64-bit Windows

Copy:

```text
VB6IDEMouseWheelAddin.dll
```

to:

```text
C:\Windows\SysWOW64
```

Then run:

```cmd
cd C:\Windows\SysWOW64
regsvr32 VB6IDEMouseWheelAddin.dll
```

## Enabling the Add-In

After registering the DLL:

1. Start Visual Basic 6.0.
2. Select **Add-Ins** → **Add-In Manager**.
3. Locate **MouseWheel Fix** in the list of available add-ins.
4. Enable:
   - **Loaded/Unloaded**
   - **Load on Startup**
5. Click **OK**.

The mouse wheel should now work in VB6 code windows.

## Troubleshooting

### "MouseWheel Fix" does not appear in Add-In Manager

- Confirm that the DLL was registered successfully.
- Ensure Command Prompt was launched with Administrator privileges.
- Restart VB6 after registering the DLL.

### Registration fails

If using 64-bit Windows, verify that the DLL has been registered using the correct version of `regsvr32`.

### No scrolling occurs

- Confirm the add-in is marked as both **Loaded/Unloaded** and **Load on Startup**.
- Restart VB6.
- Run VB6 as Administrator if required by your system configuration.

## Background

This add-in was originally distributed by Microsoft as **VB6MouseWheel.exe** and documented in Microsoft Knowledge Base article KB837910. The original download link is no longer available from Microsoft, so this repository exists for preservation purposes.

## Preservation Notice

This repository is intended to preserve a useful development tool that was previously made available by Microsoft for Visual Basic 6 users. All original rights remain with their respective owners.

## References

- Original discussion: https://stackoverflow.com/questions/1039673/how-can-i-make-mousewheel-work-in-vb6-ide
- Microsoft KB837910 (archived)
