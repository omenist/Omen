<div align="center">
  <img width="360px" src="https://raw.githubusercontent.com/omenist/assets/refs/heads/main/omen-fotor-20250501134313.png" alt="Omen Logo"/>
  
  <h1>Omen</h1>
  
  <p>
    <i>
      <b>Omen</b> is an advanced, process-less PowerShell loader leveraging the <code>System.Management.Automation</code> capabilities built into the PowerShell SDK.<br/>
      Designed for flexibility and stealth, Omen enables file-less, in-memory operations and robust plugin support.
    </i>
  </p>
</div>

---

> ⚠️ **Early Development Notice**  
> Omen is in a very early stage of development. Code, plugins, APIs, and features are subject to major changes and may break with future updates.

---

## 🚀 Features

- **Encrypted TCP Connection**  
  Secure communication with strong encryption for all payload transfers.

- **Process-less PowerShell Reverse Shell**  
  Achieve remote access without spawning additional processes.

- **Process-less File Loader (PE Support)**  
  Load executables and DLLs directly into memory—no files touch disk.

- **File-less Operations**  
  All scripts and payloads are executed completely in-memory.

- **Plugin Support**  
  Extend functionality with PowerShell script-based plugins.

- **Script Catalogue**  
  Organize and manage a collection of reusable scripts.

- **Automatic Script Execution**  
  Execute predefined scripts immediately upon establishing a connection.

- **Multiple Themes**  
  Switch between visual styles: Dracula, Charcoal, Light-mode, Win11, and more.

- **Payload Wrappers**  
  Deliver payloads as HTA, JS, BAT, VBS, and other formats.

- **Payload Obfuscation**  
  Supports Base64 encoding and source-level obfuscation for stealth.

---

## 🛠️ How It Works

Omen leverages the power of the **System.Management.Automation** namespace from the PowerShell SDK to execute PowerShell scripts directly within the context of your .NET application—**no external PowerShell process is spawned**. This is achieved by embedding and invoking the PowerShell engine within your C# code, allowing scripts to run in-memory, which enhances stealth and reduces the attack surface associated with process creation.

### Key Technical Details

- **No External PowerShell Process:**  
  Omen uses `System.Management.Automation` to host a PowerShell runspace in the current process. Scripts are loaded and executed internally, so `powershell.exe` or `pwsh.exe` never appear as child processes.

- **C# & .NET SDK:**  
  The loader is built using C# and the .NET SDK, making it easy to integrate, extend, or modify for your own use cases.

- **Costura.Fody for Embedding:**  
  If you need to embed the PowerShell Automation DLLs directly into your payload (to avoid external dependencies), simply add the [Costura.Fody](https://www.nuget.org/packages/Costura.Fody/) NuGet package to your project. This tool automatically merges referenced DLLs into your executable at compile time, ensuring your payload is fully self-contained.

### Example Usage Pattern

1. Reference the **System.Management.Automation** assembly in your C# project.
2. Use the PowerShell SDK API to create and invoke runspaces, passing in scripts or commands as needed.
3. (Optional) Add Costura.Fody via NuGet to embed dependencies.
4. Build your project—your payload can now load and execute PowerShell scripts in-memory, without ever spawning a PowerShell process.

---

<div align="center">
  <h2>Overview</h2>
  <p>
    Omen is crafted for researchers, red teamers, and enthusiasts who require stealthy, in-memory operations with a focus on extensibility and reliability.<br>
    <b>Note:</b> Usage of Omen is intended for authorized testing and educational purposes only.
  </p>
</div>

---

## 📚 Documentation

- [Wiki](https://github.com/omenist/omen/wiki)  
- [API Reference](#) (to be added)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to check the [issues page](https://github.com/omenist/omen/issues) and submit pull requests.

---

## ⚖️ License

Distributed under the GNU General Public License. See [LICENSE](LICENSE) for more information.

---
