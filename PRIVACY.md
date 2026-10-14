Privacy Policy – Snicker Tweaker Optimizer

Last updated: 14 October 2026

Snicker Tweaker Optimizer is a Windows tool that scans your PC and applies reversible performance tweaks. It has no accounts, no telemetry, no analytics and no advertising, and it does not collect or send your personal data or hardware information anywhere.

What stays on your PC

Everything the app learns about your PC (hardware scan, installed games, startup items, benchmark results, your language/theme choice, and the original values it backs up before a tweak) is stored only on your computer:

C:\ProgramData\SnickerTweaker\ – backups, settings and the log file
%LOCALAPPDATA%\SnickerTweaker\ – the extracted app files

Reports and diagnostics zips ("Export PC report", "Save diagnostics") are written to your Desktop only when you click the button. They are never uploaded. You decide whether to share them.

Network connections the app makes
Update check (GitHub). When the app starts (can be turned off in Settings > Updates) or when you click "Check now", it requests https://api.github.com/repos/mart88e9/SnickerTweakerOptimizer/releases/latest. GitHub receives your IP address and the request itself, as with any web request, and handles it under GitHub's privacy statement. The app sends no identifier, hardware or usage data.
Update download (GitHub). Only if you click Install, the app downloads SnickerTweakerOptimizer.exe from this project's GitHub Releases and verifies its SHA-256 checksum before installing it.
Network tests you start yourself. The Benchmark and Network pages ping your router and public DNS servers when you run those tests.
Windows Update driver check and winget installs. These are run by Windows itself (Microsoft's services) when you click them.
Links. Buttons such as "Check for updates" on the Drivers page open the vendor's website in your browser. The app sends nothing to those sites.
Third parties

The only service the app contacts on its own is GitHub (above). There are no third-party SDKs, trackers or ad networks.

Your control
Turn off the automatic update check in Settings > Updates.
"Undo everything" reverts the tweaks; deleting the exe and C:\ProgramData\SnickerTweaker removes everything the app stores.
Changes

If this policy changes, the new version will be published in this repository with an updated date.

Contact

Open an issue at https://github.com/mart88e9/SnickerTweakerOptimizer/issues
