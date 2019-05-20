# Exercise 5

These exercises are meant to get you familiar with basic PowerShell concepts and syntax.

Tips to maximise your learning:

- Type *everything* by hand - don't copy paste.
- Examine each command/line as you type it - try to guess what it does and confirm/check with `[Enter]`.
- Don't skip anything.
- If a command produces an error, try to read the error messages and understand why.

## Set Execution Policy

```powershell
Get-ExecutionPolicy
Set-ExecutionPolicy RemoteSigned
```

## ISE

Open PowerShell ISE

```powershell
ise
[Enter]
```

(Or find it using the Start Menu)

## Get familiar with the ISE

Write a simple script using just a couple of commands.

Try to run the script both in full (`[F5]`) and selected lines (`[F8]`). 

## Write a script

Write scripts which takes a some input and executes accordingly

Try some of these suggestions or come up with your own:

- List all files from a given folder which are ...
- Save a list of running services (selected properties) to a CSV file.
- Open a CSV file and process the data using where, select, and sort.
- Count the number of running process matching the input criteria.

You can use this as a header to get started:

```powershell
param (
    [Parameter(Mandatory=$True)]
    [string]
    $Folder
)
```

## Iteration and condition

Write more scripts using the `if` and `ForEach-Object` commands:

1. Get a list of processes
1. Loop over them
1. Display the `ProcessName` only if `Handles` are above `100`
