# Exercise 3

These exercises are meant to get you familiar with basic PowerShell concepts and syntax.

Tips to maximise your learning:

- Type *everything* by hand - don't copy paste.
- Examine each command/line as you type it - try to guess what it does and confirm/check with `[Enter]`.
- Don't skip anything.
- If a command produces an error, try to read the error messages and understand why.

## Exploring Objects

```powershell
Get-Service | Get-Member
```

## Projection (Select)

```powershell
help select -Online
Get-Service | Select-Object -Property Name, Status
gsv | select Name, Status
gsv | select -First 5
gsv | select -Skip 5 -First 5
```

## Filter (Where)

```powershell
help where -Online
Get-Service | Where-Object -Property Status -EQ -Value Stopped
Get-Service | Where-Object Status -eq "Stopped"
Get-Service | where Status -eq 'Stopped'
Get-Service | Where-Object {$_.Status -eq "Stopped"}
gsv | where {$_.Status -eq "Stopped"}
gsv | ? Status -eq Stopped
```

## Order (Sort)

```powershell
help sort -Online
Get-Service | Sort-Object -Property Name
Get-Service | Sort-Object -Property Status,Name -Descending
Get-Service | Sort-Object -Property Name -Descending
```

## Format

```powershell
help fl -Online
help ft -Online
gsv | select Name, Status | Format-List
gsv | select Name, Status | fl
gsv | select Name, Status | Format-Table
gsv | select Name, Status | ft
```

## Combine Select, Where, and Sort

- List services
- Pick only a few properties
- Filter by a property
- Sort them
- **All in one line**...

- List only .dll files in System32 (`$env:windir\System32`) which starts with the letter `d` and sort them by file size.
- **All in one line**...
- Try this using both the `-Filter` parameter of `dir` and the `where` command.
