# Snicker Tweaker Optimizer

**Reversible Windows tweaks that match your gaming PC.**

**Download:** get the latest `SnickerTweakerOptimizer.exe` from the [Releases page](https://github.com/mart88e9/SnickerTweakerOptimizer/releases/latest). Double-click it and accept the Administrator prompt. The app can update itself (Settings > Updates).

© 2026 mart88e9. Released under the [MIT License](LICENSE.md). See the [Privacy Policy](PRIVACY.md) and the [change history](CHANGELOG.md).

**Easiest way:** double-click `SnickerTweakerOptimizer.exe` and accept the Administrator prompt.

A Hone-style optimizer for Windows 10/11 gaming PCs. On every launch it scans your hardware automatically and only shows and recommends the tweaks that suit it (tuned first on an i5-11400 + RTX 3060 Ti + 32 GB DDR4 desktop, but it adapts to laptops, AMD and Intel CPUs, AMD and NVIDIA GPUs, low-RAM and HDD systems).

## Dark / light theme
Click the sun/moon button in the title bar (next to EN | DA) to switch between the dark and light theme. The window reloads on the same page and your choice is remembered.

## Settings page
Open **Settings** at the bottom of the sidebar.
- **Restore**: shows the result of the last "Undo everything" (restored / partial / failed, checked after the undo).
- **Language** (Dansk / English) and **Theme** (Dark / Light): the window reloads on the same page.
- **Security**: Undo all tweaks, and Create a restore point.
- **Support**: Save diagnostics writes a zip to your Desktop (app version, Windows and hardware info, log, tweak status; no personal files, nothing is sent anywhere) and Export PC report.
- **Advanced** (click to open): open the data folder, reset app settings (language, theme, Games settings; tweaks and backups are not touched), restart the PC.
- **Installation**: how to remove the app (it is portable).

## Games page
Open **Games** in the sidebar. It lists 29 popular games as cards with search and filters (installed / not installed / optimised, tier, genre) and finds the ones installed on your PC (Steam libraries, Epic, Riot and other common folders).
- **Optimise** on a game page applies the chosen preset (Balanced, Competitive or Max FPS): permanent High CPU priority, optionally High disk priority, the dedicated GPU on hybrid-graphics laptops, and Windows fullscreen optimisations off. The original values are saved and **Restore defaults** puts them back.
- **Games with anti-cheat** (Valorant, Fortnite, Apex and similar) only get the graphics-card choice. Their process is never touched.
- **Counter-Strike 2** also gets editable config lines written to `autoexec.cfg` inside a marked block (a backup is made first), plus saved presets and share codes.
- Every game page shows launch options (copy button), in-game setting recommendations and network tips. Launch options and in-game settings are never changed automatically.
- **Auto Game Mode** (switch on the Games page) raises a supported game's priority to High when it starts, while Snicker Tweaker is open. Nothing is frozen or closed.
- Tier A = full profile, Tier B = system-level changes + guide, Tier C = guide only.

## Benchmark page (before / after)
Open **Benchmark** in the sidebar. Click **Run BEFORE test**, apply your tweaks (restart if asked), then click **Run AFTER test**. It never opens a game: it runs small built-in tests (CPU single/multi-thread, memory bandwidth, timer resolution and wake-up delay, disk write and small-file speed, ping to your router, idle CPU/RAM/process/service counts) in a background process and shows Before / After / Change with an overall figure. Results are saved, can be exported to a text report, and a few percent difference between runs is normal noise. Texts are available in English and Danish.

## How to run
Download SnickerTweakerOptimizer.exe from the Releases page. It is a single portable file, there is nothing to install or extract.
Double-click SnickerTweakerOptimizer.exe and accept the Administrator (UAC) prompt.
If nothing opens, check %TEMP%\SnickerTweaker-error.log. If Windows SmartScreen or your antivirus complains, that is expected for an unsigned tweak tool: click More info > Run anyway. The full source is in this repository as plain text (SnickerTweaker.ps1), so you can read every line first.

## What is inside
- **Dashboard**: automatic PC scan (CPU, GPU, RAM, storage, board/BIOS, OS, display, network), a hardware profile (Desktop or Laptop, Entry-level / Mainstream / High-performance), live CPU/RAM/GPU readout, an "optimized" score ring, scan findings (XMP off, Resizable BAR off, laptop/hybrid-GPU/X3D/Wi-Fi advice, etc.) and an Export Report button (saves a text report to your Desktop).
- **FPS**: 38 latency and performance tweaks (power plan, CPU parking/boost, MMCSS, GPU scheduling, timer resolution, network latency, and more).
- **Hardware** (new in 1.1): 6 tweaks that only appear when your PC can use them: plugged-in-only performance for laptops, NVIDIA performance clocks, AMD Radeon ULPS off, larger NTFS cache for 16 GB+ RAM, SSD prefetch off, wired-Ethernet energy saving off.
- **Registry**: 20 registry tweaks (mouse acceleration, input, shutdown speed, visual effects, background apps, update behaviour).
- **Debloat**: 26 debloat and privacy tweaks (telemetry, ads, Widgets, Copilot, Edge boost, unused services, preinstalled apps).
- **Startup**: lists startup apps (registry, Startup folders) and logon/boot scheduled tasks with an estimated boot impact, and lets you turn each one off or on. Nothing is deleted; it uses the same switch as Task Manager. Microsoft's own tasks are not listed.
- **Boost-Up**: one-click cleaners (temp files, shader caches, update cache, TRIM, DNS) and permanent High priority for a game executable.
- **Backups**: restore point button, Revert ALL, and an activity log.

Tweaks that do not suit your PC are hidden automatically, and the recommendation set is scaled to it. Examples:
- Laptops: power-hungry tweaks are not recommended; use "Max Performance While Plugged In" instead (battery life stays untouched).
- AMD X3D CPUs: the Game Bar tweak is hidden (AMD's V-Cache driver needs Game Bar).
- GPU scheduling (HAGS) is only offered on GPUs that support it; MPO only on NVIDIA.
- Memory compression and kernel-in-RAM tweaks only with 16 GB or more RAM.
- Widgets tweak on Windows 11 only, News and Interests on Windows 10 only.
- Entry-level PCs get visual-effects and transparency tweaks recommended; SysMain off is recommended on 8 GB SSD systems.

## Safety
- Every tweak saves your original values to `C:\ProgramData\SnickerTweaker\state.clixml` and can be toggled back off.
- Snicker Tweaker offers to create a Windows restore point before the first change.
- Moderate and Advanced tweaks are NOT part of "Apply Recommended".
- Removing preinstalled apps cannot be undone by Snicker Tweaker (reinstall from the Microsoft Store if needed).
- "Disable Memory Integrity (HVCI)" lowers security. Leave it off unless you know why you want it.
- Restart Windows after applying tweaks marked "Reboot".

## Do these by hand (cannot be scripted safely)
**BIOS**: enable XMP/DOCP, enable Above 4G Decoding + Re-Size BAR, keep the BIOS updated.
**NVIDIA Control Panel > Manage 3D Settings**: Power management = Prefer maximum performance, Low Latency Mode = On, Shader Cache = Unlimited, Texture filtering quality = High performance.
**Windows**: set your monitor to its maximum refresh rate, install games on an SSD/NVMe, close launchers and overlays while playing.

## Building SnickerTweakerOptimizer.exe
1. Keep `SnickerTweaker.ps1`, `Build-EXE.bat` and the `build` folder together.
2. Double-click `Build-EXE.bat`. It uses the C# compiler that already ships with Windows (no downloads needed) and produces `SnickerTweakerOptimizer.exe` with the script embedded and an "always run as Administrator" flag.
3. Run `SnickerTweakerOptimizer.exe` and accept the Administrator prompt. `Launch-SnickerTweaker.bat` still works as before, without building anything.

Note: `SnickerTweakerOptimizer.exe` is unsigned, so Windows Defender or SmartScreen may flag or block it on first run — this is common for any tool that edits the registry and bypasses PowerShell's execution policy, even a harmless one. Read `SnickerTweaker.ps1` yourself (it's plain text) to confirm what it does, and if Defender blocks the exe, check Windows Security > Protection History for the exact detection name before deciding whether to allow it. `Launch-SnickerTweaker.bat` is less likely to be flagged than the compiled exe.

## Honest expectations
On an RTX 3060 Ti system the biggest real gains come from XMP, Resizable BAR, the right power plan, and a clean driver. Most registry tweaks give small improvements in frame-time consistency and input latency, not big FPS jumps. Treat any optimizer that promises "+50% FPS" with suspicion.

## Language / Sprog
The app now ships in **English and Danish (Dansk)**. English is the default. Use the **EN | DA** switch in the title bar to change language at any time; the choice is remembered. The window reloads on the same page when you switch.
All Danish text lives in the `$script:DaPack` block inside `SnickerTweaker.ps1` (one `English|||Danish` pair per line), so you can edit translations or add more languages there. Log files stay in English. If you build the EXE, run `Build-EXE.bat` again so the exe includes the Danish pack.

## Taskbar name and icon
The taskbar right-click menu and "Pin to taskbar" now show **Snicker Tweaker Optimizer** with the Snicker icon instead of "Windows PowerShell". If you pinned an older copy, unpin it, start the app and pin it again.

## New pages (sidebar)
- **Check** - Gaming Check: pass/fail list of what hurts FPS right now (RAM speed / XMP, Resizable BAR, power plan, Game Mode, Game DVR, Game Bar, GPU scheduling, mouse acceleration, overlays and background apps, free disk space, SSD/TRIM, uptime, startup entries, Wi-Fi). Each failing item has a fix button, plus "Fix All Fixable".
- **BIOS** - step-by-step guide for XMP/DOCP, Resizable BAR + Above 4G Decoding and BIOS updates, with menu names for ASUS, MSI, Gigabyte and ASRock boards and a "Restart into BIOS" button. It also warns if Windows is on an MBR disk (do not turn CSM off).
- **Network** - ping and jitter test, DNS benchmark with one-click "Use this DNS" (and reset to automatic), and the TCP/network latency tweaks.
- **Repairs** - SFC, DISM, Windows Update reset, network stack reset and a read-only disk check.
- **Install** - one-click winget installs of gaming runtimes (Visual C++, DirectX, .NET) and common gaming apps. Needs winget ("App Installer") which is built into current Windows 10/11.
All new pages are available in English and Danish.

## Code signing policy
Free code signing provided by [SignPath.io](https://signpath.io), certificate by [SignPath Foundation](https://signpath.org).

- **Authors, reviewers and approvers:** [mart88e9](https://github.com/mart88e9) (sole maintainer; every release is approved by hand before it is signed).
- **What is signed:** only `SnickerTweakerOptimizer.exe` files built from this repository's source by the project's automated GitHub Actions build.
- **Privacy:** see the [Privacy Policy](PRIVACY.md). The app collects no data; its only connection is an optional update check to GitHub.
