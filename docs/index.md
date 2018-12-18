# The Hardening Community PowerShell Module

![Banner](https://hardening.netboot.fr/content/images/banner.png)

[![PSGallery][img-psgallery-badge]][psgallery]
[![Chocolatey][img-chocolatey-badge]][chocolatey]
[![Nuget][img-nuget-badge]][nuget]

## Overview

This is a community project that provides a powerful command-line interface for many security-related configurations, providing complete basic protection.

## Module Build Status

| Branch   | AzurePipelines CI | Code Coverage |
| -------- | ----------------- | ------------- |
| stable   |                   |               |
| unstable |                   |               |

## Supported Backends

- **[Microsoft Intune](https://hardening.netboot.fr/configuration/microsoft-intune/overview/)** - Cloud-based enterprise mobility management tool
- **[Powershell DSC](https://hardening.netboot.fr/configuration/powershell-dsc/overview/)** - Configuration management tool that extends the existing functionality of Windows PowerShell.
- **[Powershell](https://hardening.netboot.fr/configuration/powershell/overview/)** - Task automation and configuration management framework.
- **[Ansible](https://hardening.netboot.fr/configuration/ansible/overview/)** - Open-source software configuration management tool.
- **[Puppet](https://hardening.netboot.fr/configuration/puppet/overview/)** - Open-source software configuration management tool.

## Documentation

Full documentation for the module is located at [https://hardening.netboot.fr](https://hardening.netboot.fr)

## Installation

To install the module from PowerShell Gallery, use the PowerShell Cmdlet:

```powershell
Install-Module -Name HardeningCore
```

For more detailed instructions on installing Hardening PowerShell , please refer to the installation guide [installation guide](https://hardening.netboot.fr/user/install/).

## Cmdlets

A list of Cmdlets in the Hardening PowerShell module can be found by running the following PowerShell commands:

```powershell
Import-Module -Name HardeningCore
Get-Command -Module HardeningCore
```

Help on individual Cmdlets can be found in the built-in Cmdlet help:

```powershell
Get-Help -Name Get-HCoreAccountPolicy
```

The details of the cmdlets contained in this module can also be found in the Cmdlet section in the documentation.

## Contributing

This project exists thanks to all the people who contribute. Development of Hardening happens at [GitHub](https://github.com/HardeningPS).

You're highly encouraged to participate in the development of Hardning powershell module. If you don't like GitHub (for some reason) you're welcome to send regular patches.

Be sure to also read the [Contributing](https://hardening.netboot.fr/user/contributing/) section in the documentation.

---
_This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments._


[psgallery]:https://www.powershellgallery.com/packages/HardeningCore
[nuget]:https://www.nuget.org/packages/HardeningCore
[chocolatey]:https://chocolatey.org/packages/HardeningCore
[img-psgallery-badge]:https://img.shields.io/powershellgallery/dt/HardeningCore.svg?style=for-the-badge&label=PSGallery
[img-chocolatey-badge]:https://img.shields.io/chocolatey/dt/HardeningCore.svg?style=for-the-badge&label=Chocolatey
[img-nuget-badge]:https://img.shields.io/nuget/dt/HardeningCore.svg?style=for-the-badge&label=Nuget
