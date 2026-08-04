# Changelog

## TuningWin11(wowo89) 8.1 25H2 - 26.07.2026

Changes compared with version 8.0:

- Created version 8.1 based on version 8.0.
- Renamed the main BAT script to `TuningWin11 8.1(wowo89).bat`.
- Updated the GUI so it launches the 8.1 BAT script.
- Updated the application title, header and version messages from 8.0 to 8.1.
- Fixed the Windows Search warning saying that search indexing had been disabled after applying tuning.
- Changed the WSearch service configuration from delayed start to automatic start and start-after-profile behavior.
- Removed Search from the list of background apps blocked by tuning, because that could bring back the disabled indexing warning after restart.
- Added `TuningWin11 Search Indexing Guard`, a logon task that keeps local Windows Search indexing active without restoring Bing/web search tweaks.
- Fixed an issue where the 8.0 debloat could remove or block Microsoft Phone Link / Smartphone-Link.
- Removed `Microsoft.YourPhone` from the default list of preinstalled apps to remove.
- Added `APP\phone_link_repair.ps1` to restore Bluetooth services, notifications, app permissions, Connected Devices Platform and settings required by Phone Link.
- Options 2, 8 and 13 now run Phone Link compatibility repair. Option 13 can also open Microsoft Store if Phone Link was previously uninstalled.
- Added a debloat prompt asking whether Phone Link / Smartphone-Link should be preserved or removed.
- The preserve option runs the safer 8.1 debloat variant with Phone Link exceptions. The remove option adds `Microsoft.YourPhone` to the removal list.
- Improved multilingual GUI question dialogs so Yes/No answers are displayed in Polish, English or German according to the selected application language, not the Windows system language.
- Added `APP\PhoneLinkRepairTool.exe`, a small graphical standalone Phone Link / Smartphone-Link repair tool.
- Added `APP\windows_update_repair.ps1`, which removes old Windows Update blocks from version 8.0, including entries that caused Windows to say updates were managed by an organization.
- Option 2 now unlocks Windows Update before further tuning and no longer sets `SetDisableUXWUAccess` or `NoAutoUpdate`, so updates can install normally.
- Removed Windows Update policies from direct GUI debloat that could block installation or grey out update settings.
- Added `APP\windows_update_manual_only.ps1` for users who choose manual-only Windows Update behavior.
- Replaced the light Windows Update cache cleanup in option 4 with a fuller reset of Windows Update, BITS, Cryptographic Services and Windows Installer, plus renaming `SoftwareDistribution` and `catroot2`.
- Verified that Microsoft DirectX End-User Runtimes June 2010 remains the current DirectX Legacy package, so `APP\directx` remains unchanged.
- Updated Visual C++ Redistributable to `APP\Visual-C-Runtimes-All-in-One-Jun-2026`; v14 x86/x64 packages were updated to version 14.51.36247.0 from official Microsoft links.
- Improved the Visual C++ installer so it installs an explicit list of correct packages and does not run duplicated older installers.
- Split option 4 and option 5 more clearly: option 4 handles system cleanup and Windows Update reset, while option 5 handles deep scan and system repair without duplicating cleanup tasks.
- Extended option 4 with safe cleanup of Delivery Optimization cache, Windows Error Reporting reports, thumbnails, icon cache, DirectX Shader Cache and additional user/system TEMP locations.
- Improved Windows Update reset in option 4 so previous `SoftwareDistribution.old` and `catroot2.old` folders are removed before another reset.
- Added clickable links to `https://wowo89.de` and `https://zawalka.com` in the GUI header.
- Added a clickable `License / Licencja / Lizenz` link in the GUI header. It opens an embedded license window in the language selected in the application.