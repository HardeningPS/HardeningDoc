# Install

This repository contains a folder named [HardeningCore](https://github.com/HardeningPS/HardeningCore/tree/stable/HardeningCore). The folder needs to be installed into one of your PowerShell Module Paths using one of the installation methods outlined in the next section. To see the full list of available PowerShell Module paths, use `$Env:PSModulePath.Split( ';' )` in a PowerShell terminal window.

Common PowerShell module paths include:

1. Current User: `%USERPROFILE%\Documents\WindowsPowerShell\Modules\`
1. All Users: `%ProgramFiles%\WindowsPowerShell\Modules\`
1. OneDrive: `$Env:OneDrive\Documents\WindowsPowerShell\Modules\`

## Option 1: PowerShell Gallery Installation (Recommended)

1. Ensure you have the [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) or greater installed.
1. Open a PowerShell console with the *Run as Administrator* option.
1. Run `Set-ExecutionPolicy` using the parameter *RemoteSigned* or *Bypass*.
1. Run `Install-Module -Name 'HardeningCore' -Scope 'CurrentUser'` to download the module from the PowerShell Gallery. Note that the first time you install from the remote repository it may ask you to first trust the repository.

## Option 2: PowerShell Gallery Download

1. Ensure you have the [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) or greater installed.
1. Open a PowerShell console with the *Run as Administrator* option.
1. Run `Set-ExecutionPolicy` using the parameter *RemoteSigned* or *Bypass*.
1. Run `Save-Module -Name 'HardeningCore' -Path <path>` to download the module from the PowerShell Gallery. Note that the first time you install from the remote repository it may ask you to first trust the repository.
1. Copy the contents of the HardeningCore module folder onto your workstation into the desired PowerShell Module path.

## Option 3: Manual Installation

1. Download the latest [release version](https://github.com/HardeningPS/HardeningCore/releases) to your workstation.
1. Copy the contents of the *HardeningCore* folder onto your workstation into the desired PowerShell Module path.
1. Open a PowerShell console with the *Run as Administrator* option.
1. Run `Set-ExecutionPolicy` using the parameter *RemoteSigned* or *Bypass*.

## Verification

PowerShell will create a folder for each new version of any module you install. It's a good idea to check and see what version(s) you have installed and running in the session. To begin, let's see what versions of the HardeningCore Module are installed:

```powershell
Get-Module -ListAvailable -Name 'HardeningCore'
```

The `-ListAvailable` switch will pull up all installed versions from any path found in `$Env:PSModulePath`. Check to make sure the version you wanted is installed. You can safely remove old versions, if desired.

To see which version is currently loaded, use:

```powershell
Get-Module -Name 'HardeningCore'
```

If nothing is returned, you need to first load the module by using:

```powershell
Import-Module -Name 'HardeningCore'
```

If you wish to load a specific version, use:

```powershell
Import-Module -Name 'HardeningCore' -RequiredVersion $version
```

Where `$version` is set to the desired version number.
