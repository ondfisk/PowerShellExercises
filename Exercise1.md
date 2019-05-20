# Exercise 1

These exercises are meant to get you familiar with basic PowerShell concepts and syntax.

Note an item in angle brackes ([]) typically means a key so `[Win] + x` means "hold down the Windows key and hit x".

Tips to maximise your learning:

- Type *everything* by hand - don't copy paste.
- Examine each command/line as you type it - try to guess what it does and confirm/check with `[Enter]`.
- Don't skip anything.
- If a command produces an error, try to read the error messages and understand why.

## Open your PowerShell command prompt

### User Mode

```shell
[Win] + x + i
```

In Windows Explorer:

```txt
[Shift] + [Right Click] -> Open PowerShell window here
```

### Admin Mode

```txt
[Win] + x + a
```

## Open Command Prompt

```shell
[Win] + r
cmd
[Enter]
```

## Compare PowerShell and Command Prompt

In both shells run

```shell
ping www.microsoft.com
ipconfig
```

In PowerShell run

```powershell
Get-Command -CommandType Application
```

Close your Command Prompt

## Check Your PowerShell Version

```powershell
$PSVersionTable
```

## Run A Couple Of Commands

```powershell
Get-Service
Get-Process
Get-Process -Name power*
Stop-Process # hit [CTRL]+C to exit
Stop-Process -Name powershell
Stop-Process -Id [number]
```

## Clear Screen

```powershell
Clear-Host
cls
clear
```

## Tab Completion

PowerShell supports tab completion so most commands can be auto completed by typing a few (defining) characters and hitting tab

```powershell
get-ser # [Tab]
get-se # [Tab][Tab][Tab]
Get-Service -n # [Tab]
```

## Explore PowerShell Help

```powershell
Get-Help
Get-Help Get-Process
help *log*
help *event*
help about_*
help about_Core_Commands -ShowWindow
```

### Explore Help Switches

```powershell
Get-Help -Name "Get-Process" -Detailed
Get-Help -Name "Get-Process" -Full
Get-Help -Name Get-Process -ShowWindow
Get-Help -Name Get-Process -Online
Get-Help -Name Get-Process -Parameter Name
```

### Compare

```powershell
Get-Help -Name Get-Process
help Get-Process
Get-Help Get-Process | more
```

### Update Help (admin only)

```powershell
Update-Help
```

## Explore Commands

```powershell
Get-Command -Name Get-*
Get-Command -Verb Get
Get-Command -Noun Csv
Get-Command -Noun *Object
Get-Command -Module Microsoft.PowerShell.Utility
Get-Command -Noun Object -Module Microsoft.PowerShell.Utility
```

## Explore Aliases

```powershell
Get-Alias
Get-Alias -Name ls
Get-Alias -Name dir
Get-Alias -Definition Get-ChildItem
```

## Explore Default Parameters

```powershell
help ls
ls -Filter .*
ls .*
```

## Explore Switches

```powershell
Set-Location $env:USERPROFILE
cd .\Documents\
ls -File
ls -Directory
ls -d
ls -f
ls -di
```

## Common Parameters

PowerShell has a set of common parameters which are automatically available for all cmdlets.

```powershell
Remove-Item *.* -WhatIf
Remove-Item "foo" -ErrorAction SilentlyContinue
help about_CommonParameters
```