# 🪟 WinGet Bootstrap & Tool Installer for Windows Sandbox

This project provides a ready-to-use configuration for [Windows Sandbox](https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-sandbox/windows-sandbox-overview). It bootstraps the WinGet PowerShell module and installs essential applications such as **Tailscale**, **OpenSSH Preview**, and **Tera Term** upon startup.

## 📦 Included Files

- `Configuration.wsb`  
  - A Windows Sandbox configuration file.
  - Contains a `LogonCommand` that automatically installs the required tools via PowerShell and WinGet when the sandbox starts.

## 🚀 What It Installs

```powershell
# Setup WinGet PowerShell module
Install-PackageProvider -Name NuGet -Force
Install-Module -Name Microsoft.WinGet.Client -Force -Repository PSGallery
Repair-WinGetPackageManager

# Install applications
winget install -e --accept-package-agreements --id Tailscale.Tailscale
winget install -e --accept-package-agreements --id Microsoft.OpenSSH.Preview
winget install -e --accept-package-agreements --id TeraTermProject.teraterm5
```

## 📝 How to Use

1. Clone or download this repository as a ZIP file.
2. Double-click the `Configuration.wsb` file to launch Windows Sandbox.
3. The sandbox environment will automatically install the listed tools on startup.

## 🛠 Use Cases

- Rapid provisioning of clean, temporary Windows environments
- Automating setup for IT or security testing
- Reproducible and disposable dev/test environments
- Installing common networking and remote access tools without manual setup

## ⚠️ Notes

- Some tools may require an active internet connection during installation.
- This setup assumes the host system has access to PowerShell Gallery and the Microsoft Store source for WinGet packages.
- WinGet may require initial setup time in fresh environments.

## 📄 License

MIT License
