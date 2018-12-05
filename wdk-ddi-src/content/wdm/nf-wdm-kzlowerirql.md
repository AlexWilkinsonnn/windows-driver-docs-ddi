---
UID: NF:wdm.KzLowerIrql
title: KzLowerIrql function
author: windows-driver-content
description: Restores the IRQL on the current processor to its original value. 
ms.assetid: 516b6d64-447e-427e-a544-88b9dc8bea66
ms.date: 09/30/2018
ms.topic: function
ms.keywords: KzLowerIrql, KeLowerIrql
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll:
req.irql: HIGH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	KzLowerIrql
product: Windows
targetos: Windows


ms.custom: RS5
---

# KzLowerIrql function


## -description

Restores the IRQL on the current processor to its original value. For information about IRQLs, see [Managing Hardware Priorities](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-hardware-priorities).

## -parameters

### -param NewIrql

[in] Specifies the IRQL that was returned from <a href="https://msdn.microsoft.com/library/windows/hardware/ff553079">KeRaiseIrql</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553084">KeRaiseIrqlToDpcLevel</a>.


## -returns

## -remarks
This function is same as the [**KeLowerIrql**](nf-wdm-kelowerirql.md) function.

## -see-also
