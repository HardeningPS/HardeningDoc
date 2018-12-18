# Update

## Option 1: PowerShell Gallery Update (Recommended)

If you installed the module via the PowerShell Gallery, please implement the following when you want to update to a newer version:

1. Open a PowerShell console with the *Run as Administrator* option.
1. Run `Update-Module -Name 'HardeningCore'`.

## Option 2: PowerShell Gallery Download

If you deployed a saved module via the PowerShell Gallery, please implement the following when you want to update to a newer version:

1. Open a PowerShell console with the *Run as Administrator* option.
1. Run `Save-Module -Name 'HardeningCore' -Path $path` to download the module from the PowerShell Gallery. Note that the first time you install from the remote repository it may ask you to first trust the repository.
1. Copy the contents of the HardeningCore module folder into your workstation into the desired PowerShell Module path.

## Option 3: Manual Installation

If you deployed the module via download from GitHub, please implement the following when you want to update to a newer version:

1. Download the latest [release version](https://github.com/HardeningPS/HardeningCore/releases) to your workstation.
1. Copy the contents of the *HardeningCore* folder onto your workstation into the desired PowerShell Module path.
