# 🔍 twin-hunt

A lightweight, terminal-based duplicate file finder built with Python. This tool scans any Windows directory (via WSL2 or native Python) and identifies identical files based on their digital fingerprint (SHA-256), ignoring filenames.

## 🚀 Features
- **Deep Scan:** Uses SHA-256 hashing to find true duplicates, even if they have different names.
- **Memory Efficient:** Reads large files (videos/high-res photos) in small chunks to prevent RAM spikes.
- **Windows Optimized:** Designed to be called from the Windows Terminal to scan NTFS drives via WSL2.
- **Safety First:** Includes a "Dry Run" mode and user confirmation before any file operations.

## 🛠️ How it Works
1. **Walks** through the target directory and all subfolders.
2. **Filters** files to find potential matches.
3. **Hashes** file contents to generate a unique "fingerprint."
4. **Groups** files with identical hashes into a dictionary.
5. **Reports** all "twins" found and offers to clean them up.

## 📦 Requirements
- Python 3.x
- No external libraries required (uses built-in `os`, `hashlib`, and `collections`).
- *Optional:* `send2trash` if you prefer moving files to the Recycle Bin instead of permanent deletion.

## 💻 Usage

### Running via WSL2
To scan your Windows "Memos" folder from a Windows Terminal:
```powershell
wsl python3 /path/to/functions.py "C:\.Memos\MakeUseOf\Models"
