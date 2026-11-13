# DFIsolPolicy

DFIsolPolicy blocks the app-zygote spawn path for the apps you choose. On many rooted devices, apps that fork their isolated processes from the app zygote crash-loop or refuse to run (banking and carrier apps are the usual victims). DFIsolPolicy denies that spawn path inside system_server, so the app starts as a normal process and behaves again.

Features:
* Per-package deny list: pick exactly which apps get the treatment; nothing else is touched
* Search and filter for long app lists
* One tap on APPLY CHANGES writes the list and takes effect immediately, no reboot
* Live status box (module active state, deny tester, DroidForge emblem)
* Built-in tester: binds its own always-denied isolated service and reports whether the deny actually fired (long-press the status box for diagnostics)
* Xposed API 93 ready; legacy Xposed API; recommended scope: System Framework (android) + DFIsolPolicy
* The app itself never asks for root; the hook runs through your LSPosed framework
* Phone and tablet layouts; gesture and 3-button navigation supported
* Dark embossed UI in the DroidForge style, with a density-matched emblem that renders sharp on every screen
* Contact Us dialog with DroidForge social channels
* No ads, no tracking, works fully offline

Requirements:
* Android 10 or newer
* Root with LSPosed (or a compatible fork such as Vector) installed and running
* Enable DFIsolPolicy in LSPosed, set the recommended scope, reboot once

How to use:
1. Enable the module in LSPosed and reboot
2. Open DFIsolPolicy and tick the apps you want (banking and carrier apps first)
3. Tap APPLY CHANGES
4. Open the app you fixed; the crash loop is gone

Based on Isolation Policy by MhmRdd (Apache License 2.0). Thanks To: MhmRdd.
www.droidforge.net

Changelog v1.9.10:
- Visual fix: the DroidForge emblem in the status box now ships in density-matched pixel sizes (64/96/128/192/256 px), pre-scaled for sharpness, so it renders crisp instead of pixelated.
- No functional changes; the Xposed API 93 support and the app-zygote deny hook are unchanged.
