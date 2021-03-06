---
UID: NS:hbapiwmi._SetBindingSupport_OUT
title: _SetBindingSupport_OUT (hbapiwmi.h)
description: The SetBindingSupport_OUT structure is used to report the output parameter data of the SetBindingSupport WMI method to the WMI client.
old-location: storage\setbindingsupport_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SetBindingSupport_OUT structure"]
ms.keywords: "*PSetBindingSupport_OUT, PSetBindingSupport_OUT, PSetBindingSupport_OUT structure pointer [Storage Devices], SetBindingSupport_OUT, SetBindingSupport_OUT structure [Storage Devices], _SetBindingSupport_OUT, hbapiwmi/PSetBindingSupport_OUT, hbapiwmi/SetBindingSupport_OUT, storage.setbindingsupport_out, structs-Fibre_95e0c3db-69d5-406f-98ea-6554eed922ef.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SetBindingSupport_OUT, *PSetBindingSupport_OUT
f1_keywords:
 - _SetBindingSupport_OUT
 - hbapiwmi/_SetBindingSupport_OUT
 - PSetBindingSupport_OUT
 - hbapiwmi/PSetBindingSupport_OUT
 - SetBindingSupport_OUT
 - hbapiwmi/SetBindingSupport_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SetBindingSupport_OUT
 - PSetBindingSupport_OUT
 - SetBindingSupport_OUT
---

# _SetBindingSupport_OUT structure


## -description

The SetBindingSupport_OUT structure is used to report the output parameter data of the <a href="/windows-hardware/drivers/storage/setbindingsupport">SetBindingSupport</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the SetBindingSupport_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/setbindingsupport">SetBindingSupport</a>

