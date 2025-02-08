# Nucleares-Modding-Tool
This tool allows for easier modding of the Nucleares game.

# What it does
It decompiles the `Assembly-CSharp.dll` of the game, adds the mod loader, then compiles it again. It also creates a backup of the original DLL and creates a `mods` directory.

# How to use it

1. **Install Dependencies**:
   - Ensure you have Python installed. If not, download and install it from [python.org](https://www.python.org/downloads/).
   - You will need the `dnSpy` decompiler (`dnSpy.Console.exe`) and `ilasm.exe` for the decompilation and recompilation process. Download `dnSpy` from [dnSpy GitHub](https://github.com/dnSpy/dnSpy), and ensure `ilasm.exe` is available at `C:\Windows\Microsoft.NET\Framework\v4.0.30319\ilasm.exe` (this is typically included with the .NET Framework).
   
2. **Set Up Directories**:
   - Obtain a copy of the `Assembly-CSharp.dll` file from your Nucleares game directory. This is the file the tool will modify. Make sure you have it accessible on your system.
   - Ensure the mod loader and decompiler-related files are available and configured properly.

3. **Run the Script**:
   - Save the script as a `.py` file (e.g., `mod_loader_installer.py`).
   - Open a command prompt or terminal and run the script with Python:
     ```bash
     python mod_loader_installer.py
     ```

4. **GUI Usage**:
   - **Browse for DLL**: Click the "Browse" button to locate the `Assembly-CSharp.dll` file from your game directory.
   - **Install Mod Loader**: Click the "Install Mod Loader" button to install the mod loader. The script will:
     - Backup the original `Assembly-CSharp.dll`.
     - Decompile the DLL using `dnSpy`.
     - Inject a mod loader script into `GameManager.cs` (or update it if a newer version is available).
     - Recompile the DLL using `ilasm.exe`.
     - Create a `mods` directory for custom mods.
   - **Restore Original DLL**: If needed, click the "Restore Original DLL" button to restore the backup of the `Assembly-CSharp.dll`.

5. **Log Output**:
   - Throughout the process, the script will display progress in the log section of the GUI. This includes messages such as "Successfully Decompiled," "Mod Loader Injected," and "Recompiling DLL."

# Dependencies

### **Python Dependencies:**
1. **os** – Standard Python library for file and directory manipulation.
2. **shutil** – Standard Python library for file copying and removal.
3. **subprocess** – Standard Python library for running system commands.
4. **urllib.request** – Standard Python library for making HTTP requests (used for checking updates and downloading files).
5. **tkinter** – Standard Python library for building GUI applications.
6. **tkinter.filedialog** – Part of the `tkinter` library for opening file dialogs.
7. **tkinter.messagebox** – Part of the `tkinter` library for displaying message boxes.
8. **tkinter.scrolledtext** – Part of the `tkinter` library for displaying a scrollable text area.

### **External Tool Dependencies:**
1. **dnSpy.Console.exe** – External tool used for decompiling the `Assembly-CSharp.dll`. Make sure this tool is available and properly configured.
2. **ilasm.exe** – External tool from the .NET framework for compiling the modified assembly back into a DLL.

### **URLs for Mod Loader:**
1. **https://dl.atdevs.org/nucleares-modding-tool/csharp/latest.txt** – URL to check for the latest version of the mod loader.
2. **https://dl.atdevs.org/nucleares-modding-tool/csharp/** – Base URL for downloading the mod loader script files.

### **System Requirements:**
- **Windows OS** – This script is designed for Windows and requires `ilasm.exe` to be available at `C:\Windows\Microsoft.NET\Framework\v4.0.30319\`.

Make sure to install all necessary tools and configure paths before running the script.

## License & Terms of Service
This software is provided under the Apache License 2.0.  
By using this software, you agree to both the Apache 2.0 License and the ATDevs Terms of Service:  
➡ [ATDevs Terms of Service](https://docs.atdevs.org/terms/tos.html)
