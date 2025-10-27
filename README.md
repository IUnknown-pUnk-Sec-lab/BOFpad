# BOFpad - Notepad TabState Decoder (BOF)

BOFpad is a Beacon Object File (BOF) that extracts and decodes saved tab state data from Windows 11/10 Notepad. It scans the Notepad TabState directory, extracts .bin files, and attempts to recover UTF-16LE or ASCII content to help analysts or red teamers understand what was left in open Notepad tabs — even if the tabs were unsaved.

## What It Does

Locates the %LOCALAPPDATA%\Packages\Microsoft.WindowsNotepad_* directory

Searches for .bin files under LocalState\TabState

Extracts readable content from each file:

Attempts UTF-16LE decoding

Falls back to ASCII if needed

Outputs sanitized, line-wrapped, safe strings directly to the C2 channel

## Example Output
```
========================================
   BOFpad - Notepad TabState Decoder
========================================
Author : IUnknown* pUnk Sec Lab
Version: 2.1

[*] Starting BOFpad...

[+] Scanning: C:\Users\Alice\AppData\Local\Packages\Microsoft.WindowsNotepad_8wekyb3d8bbwe\LocalState\TabState

=== tabstate_1234.bin (2048 bytes) ===
To-do List:
- Buy groceries
- Finish report for client

[i] No UTF-16LE text detected, trying ASCII fallback...
```
