A series of instructions on how to improve quality-of-life on a Windows PC.

This is written from the perspective of someone coming from a background developing on OSX/Linux, so most of these modifications are to bring parity between those operating systems and modern Windows.

# WSL2

> The Windows Subsystem for Linux (WSL) is a new Windows 10 feature that enables you to run native Linux command-line tools directly on Windows, alongside your traditional Windows desktop and modern store apps.

https://docs.microsoft.com/en-us/windows/wsl/faq

[Follow Microsoft's documentation on how to install WSL2](https://docs.microsoft.com/en-us/windows/wsl/wsl2-install).

Then, install [Ubuntu](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q) and the [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701) from the Microsoft Store app.

## Keyboard shortcut for WSL2

Navigate to `C:\ProgramData\Microsoft\Windows\Start Menu\Programs`. Create a shortcut file, then in its properties set "Target" to `C:\Users\YOUR_USERNAME_HERE\AppData\Local\Microsoft\WindowsApps\wt.exe`, "Start in" to `C:\Windows\System32`, and "Shortcut Key" to your preference.

# More WSL2 Customization

The Windows Terminal can be customized by typing `Ctrl`+`,`, which will open `settings.json`.

## Set Ubuntu to be the default profile

In `settings.json`, find the `guid` for your Ubuntu profile. It should have `"tabTitle": "Ubuntu"` as one of the properties. Replace the top level `defaultProfile` property with that guid.

## Close keyboard shortcut

Modify the `settings.json` to have a more familiar "close tab" keyboard shortcut.

```json
"keybindings": [
        {
            "command" : "closeTab",
            "keys": ["ctrl+w"]
        }
    ]
```

# Virtual Desktops

Virtual desktops are equivalent to OSX and Ubuntu's workspaces. Unfortunately, as with many features, Windows offers no easy method to customize the keyboard shortcuts for using it.

If you'd like to change the default shortcuts, download, install, and configure [Windows 10 Virtual Desktop Enhancer](https://github.com/mkrnr/keymap) AutoHotKey (AHK) script to your liking. Note that this program occasionally breaks due to the Windows updates, so you may need to check for updated forks if the linked version is no longer maintained. (You'll know it doesn't work if some or all keyboard shortcuts stop working.)

Follow [these instructions](https://blog.danskingdom.com/get-autohotkey-script-to-run-as-admin-at-startup/) to run the AHK script at startup, with admin privilages.

# Window Management

[DisplayFusion](https://www.displayfusion.com/) has several great customization features, but the most noteworthy is probably the ability to set custom keyboard shortcuts for window management. The Custom Functions in Settings > Functions can be set up to mostly emulate any window management shortcut keys users may be used to coming from OSX or Linux.