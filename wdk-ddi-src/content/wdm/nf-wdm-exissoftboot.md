---
UID: NF:wdm.ExIsSoftBoot
title: ExIsSoftBoot function (wdm.h)
description: Determines whether the system has gone through a soft restart.
old-location: kernel\exissoftboot.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExIsSoftBoot function"]
ms.keywords: ExIsSoftBoot, ExIsSoftBoot function [Kernel-Mode Driver Architecture], kernel.exissoftboot, wdm/ExIsSoftBoot
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExIsSoftBoot
 - wdm/ExIsSoftBoot
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExIsSoftBoot
---

# ExIsSoftBoot function


## -description

Determines whether the system has gone through a soft restart.

## -returns

TRUE indicates a soft restart; FALSE otherwise.

