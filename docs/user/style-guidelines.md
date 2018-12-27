# Style Guidelines

In order to provide clean and consistent code, please follow the coding conventions listed below.

## General Rules

- For all indentation, use 4 spaces instead of tab stops
- Make sure all files are encoding using UTF-8.
- When writing Markdown, if a paragraph includes more than one sentence, end each sentence with a newline. GitHub will still render the sentences as a single paragraph, but the readability of git diff will be greatly improved.
- Files must end with a newline

## PowerShell Coding Style Guideline

### Code should not contain multiple blank lines in a row

**Bad:**

```powershell
Function Get-MyValue
{
    Write-Verbose 'Getting MyValue'


    return $MyValue
}
```

The above code breaks this rule by having two new lines between the write-verbose and the return.

**Good:**

```powershell
Function Get-MyValue
{
    Write-Verbose -Verbose 'Getting MyValue'
    return $MyValue
}
```

### Opening curly brackets should not be followed by a blank line

**Bad:**

```powershell
Function Get-MyValue
{

    Write-Verbose 'Getting MyValue'

    return $MyValue
}
```

The code above breaks this rule by leaving a blank line after the opening curly brackets.

**Good:**

```powershell
Function Get-MyValue
{
    Write-Verbose -Verbose 'Getting MyValue'
    return $MyValue
}
```

### Braces should always be on a following line

**Bad:**

```powershell
if ( $connected ) {
    Write-Verbose 'Connected to server'
}
```

**Good:**

```powershell
if ( $connected )
{
    Write-Verbose -Verbose 'Connected to server'
}
```

### Each line should have less than 100 characters

**Bad:**

```powershell
$convertToCimUnjoinCredential = New-CimInstance -ClassName MSFT_Credential -Property @{Username=[string]$UnjoinCredential.UserName; Password=[string]$null} -Namespace root/microsoft/windows/desiredstateconfiguration -ClientOnly
```

**Good:**

```powershell
$Params = @{
  ClassName = 'MSFT_Credential'
  Property = @{
    Username = [string]$UnjoinCredential.UserName
    Password = [string]$Null
  }
  Namespace = 'root/microsoft/windows/desiredstateconfiguration'
  ClientOnly = $True
}
$convertToCimUnjoinCredential = New-CimInstance @Params
```

### Use verbose, easy to understand names

**Bad:**

```powershell
$rdsHost = Get-RdsHost
```

**Good:**

```powershell
$remoteDesktopSessionHost = Get-RemoteDesktopSessionHost
```

### Function names should use PascalCase and follow Noun-Verb convention if possible

**Bad:**

```powershell
function getTargetResource
{
    # ...
}
```

**Good:**

```powershell
function Get-TargetResource
{
    # ...
}
```

### Parameter names should use PascalCase

**Bad:**

```powershell
function Get-TargetResource
{
    ...
     param
     (
         ...
         $SOURCEPATH
         ...
}
```

**Good:**

```powershell
function Get-TargetResource
{
    [CmdletBinding()]
     param
     (
         ...
         $SourcePath
         ...
}
```

### Variable names should use CamelCase

Names of variables should use CamelCase

**Bad:**

```powershell
function New-Log
{
    $Message = "New log message" # should start with Low case
    Write-Host $Message
}
```

**Good:**

```powershell
function New-Log
{
    $message = "New log message"
    Write-Host $message
}
```

### Support comment-based help

When commenting functions, use comment-based help syntax

**Bad:**

```powershell
# Writes event
function New-EtwEvent
{
    param
    (
        [Parameter(Mandatory=$True)]
        [ValidateNotNullOrEmpty()]
        [String] $message,
        [ValidateSet("operational", "debug", "analytic")]
        [String] $chanel = "operational"
    )
    # Implementation
 }
```

**Good:**

```powershell
function New-EtwEvent
{
    <#
        .SYNOPSIS Writes event to ETW
        .PARAM
        message Message to write to ETW
        .PARAM
        chanel ETW channel where message should be stored
        .EXAMPLE
        New-EtwEvent -message "Attempting to connect to server" -chanel "debug"
    #>
    param
    (
        [Parameter(Mandatory=$True)]
        [ValidateNotNullOrEmpty()]
        [String] $message,
        [ValidateSet("operational", "debug", "analytic")]
        [String] $chanel = "operational"
    )
    # Implementation
 }
```

### Call cmdlets using all named parameters instead of positional parameters

**Bad:**

```powershell
Get-Childitem c:\documents *.md
```

The above code breaks this rule using by calling ```Get-ChildItem``` passing positional parameters instead of named parameters.

**Good:**

```powershell
Get-ChildItem -Path c:\documents -filer *.md
```
