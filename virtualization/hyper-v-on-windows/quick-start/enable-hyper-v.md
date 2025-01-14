---
title: Enable Hyper-V on Windows
description: Install Hyper-V on Windows 10 or Windows 11 either using the Windows control panel, PowerShell or DISM.
keywords: windows 10, windows 11, hyper-v
author: scooley
ms.author: roharwoo
ms.date: 07/29/2024
ms.topic: article
ms.assetid: 752dc760-a33c-41bb-902c-3bb2ecd9ac86
---

# Install Hyper-V on Windows

Enable Hyper-V to create virtual machines on Windows. Hyper-V can be enabled in many ways including using the Windows control panel, PowerShell or using the Deployment Imaging Servicing and Management tool (DISM). This document walks through each option.

>[!NOTE]
> Hyper-V is built into Windows as an optional feature -- there's no Hyper-V download.

## Check requirements

* Windows 10 (Pro or Enterprise), or Windows 11 (Pro or Enterprise)
* 64-bit Processor with Second Level Address Translation (SLAT).
* CPU support for VM Monitor Mode Extension (VT-c on Intel CPUs).
* Minimum of 4 GB memory.

>[!NOTE]
> The Hyper-V role **can't** be installed on Windows 10 Home or Windows 11 Home.

For more information and troubleshooting, see [Windows Hyper-V System Requirements](/virtualization/hyper-v-on-windows/reference/hyper-v-requirements).

## Enable Hyper-V using PowerShell

1. Open a PowerShell console as Administrator.

1. Run the following command:

  ```powershell
  Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
  ```

  If the command isn't found, make sure you're running PowerShell as Administrator.

1. When the installation completes, reboot.

## Enable Hyper-V with CMD and DISM

The Deployment Image Servicing and Management tool (DISM) helps configure Windows and Windows images.  Among its many applications, DISM can enable Windows features while the operating system is running.

To enable the Hyper-V role using DISM:

1. Open up a PowerShell or CMD session as Administrator.

1. Type the following command:

  ```powershell
  DISM /Online /Enable-Feature /All /FeatureName:Microsoft-Hyper-V
  ```

  ![Console window showing Hyper-V being enabled.](media/dism_upd.png)

For more information about DISM, see the [DISM Technical Reference](/windows-hardware/manufacture/desktop/dism-reference--deployment-image-servicing-and-management).

## Enable the Hyper-V role through Settings

1. Navigate to the Control Panel.

1. Select **Programs**, then **Programs and Features**.

1. Select **Turn Windows Features on or off**.

1. Select **Hyper-V** and then select **OK**.

![Windows programs and features dialogue box](media/enable-hyper-v.png)

When the installation completes you're prompted to restart your computer.

## Make virtual machines

[Create your first virtual machine](create-virtual-machine.md)
