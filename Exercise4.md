# Exercise 4

These exercises are meant to get you familiar with basic PowerShell concepts and syntax.

Tips to maximise your learning:

- Type *everything* by hand - don't copy paste.
- Examine each command/line as you type it - try to guess what it does and confirm/check with `[Enter]`.
- Don't skip anything.
- If a command produces an error, try to read the error messages and understand why.

## Built-in Values

```powershell
$false
$true
$null
```

## Built-in Variables

```powershell
$ [Tab] [Tab] [Tab]
$home
$Host
$Error
$ErrorActionPreference
$PSHOME
$env: [Tab] [Tab] [Tab]
```

## Setting and Getting a Variable

```powershell
$foo = "bar"
Write-Host $foo`

$answer = 42

Write-Host "The answer to life the universe and everything: $answer"
```

## Strings

```powershell
$h = "Hello"
$w = "world"
$h + " " + $w
"$h $w"

$st = @("Say hello", " world")
"$st"

-join($h,$w)
$h,$w -join " "
```

## If

```powershell
$good = $true

if ($good) {
    Write-Host "Good!"
}

$bad = $false

if (-not $bad) {
    Write-Host "Not bad!"
}

$bool = false

if ($bool = $true) {
    "True"
} else {
    "False"
}
```
