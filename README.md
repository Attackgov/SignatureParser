# Signature Parser

**Signature Parser** is a Windows tool that scans directories for `.exe` files and checks whether they are digitally signed. Signed files are displayed in green, unsigned files in red. This is useful for quickly verifying the authenticity of executables on your system.

## Tip
Run this using powershell for easier execution:
```
$tool = "$env:TEMP\SignatureParser.exe"
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Attackgov/SignatureParser/main/SignatureParser.exe" -OutFile $tool
Start-Process -FilePath $tool -Verb RunAs
```
---

## Requirements

- Windows 7 or higher
- Administrator privileges (required to run the tool properly)

---

## Usage

1. Download the `SignatureParser.exe` from this repository.
2. Create a file named `paths.txt` in the same folder as the executable.
3. Add one folder path per line in `paths.txt`. Example:

    ```
    C:\Program Files
    D:\Games
    E:\Tools\Utilities
    ```

4. Run `SignatureParser.exe` **as administrator**.
5. The tool will scan each folder recursively for `.exe` files:
    - **Signed files** appear in **green**
    - **Unsigned files** appear in **red**
6. After scanning, the console will freeze so you can review the results.

---

## Notes

- If `paths.txt` is missing or empty, the tool will display instructions on how to create it.
- The console will automatically maximize to fullscreen for better visibility.

---
