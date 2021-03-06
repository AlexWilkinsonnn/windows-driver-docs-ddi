---
UID: NS:wdm._MAILSLOT_CREATE_PARAMETERS
title: _MAILSLOT_CREATE_PARAMETERS (wdm.h)
description: The MAILSLOT_CREATE_PARAMETERS is used by the Windows subsystem to create a mailslot.
tech.root: kernel
ms.date: 11/06/2019
keywords: ["MAILSLOT_CREATE_PARAMETERS structure"]
ms.keywords: "*PMAILSLOT_CREATE_PARAMETERS, MAILSLOT_CREATE_PARAMETERS, MAILSLOT_CREATE_PARAMETERS structure"
req.header: wdm.h
req.include-header: Ntifs.h
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
req.typenames: MAILSLOT_CREATE_PARAMETERS, *PMAILSLOT_CREATE_PARAMETERS
f1_keywords:
 - _MAILSLOT_CREATE_PARAMETERS
 - wdm/_MAILSLOT_CREATE_PARAMETERS
 - PMAILSLOT_CREATE_PARAMETERS
 - wdm/PMAILSLOT_CREATE_PARAMETERS
 - MAILSLOT_CREATE_PARAMETERS
 - wdm/MAILSLOT_CREATE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _MAILSLOT_CREATE_PARAMETERS
 - PMAILSLOT_CREATE_PARAMETERS
 - MAILSLOT_CREATE_PARAMETERS
---

# _MAILSLOT_CREATE_PARAMETERS structure


## -description

 The MAILSLOT_CREATE_PARAMETERS is used by the Windows subsystem to create a mailslot.

## -struct-fields

### -field MailslotQuota

Pool quota that is reserved for writes to this mailslot.

### -field MaximumMessageSize

Size, in bytes, of the largest message that can be written to this mailslot.

### -field ReadTimeout

The timeout period for the read operation, specified as a relative time.

### -field TimeoutSpecified

Boolean value that specifies whether a timeout period was provided in the *ReadTimeout* member.

## -remarks

For an [IRP_MJ_CREATE_MAILSLOT](/windows-hardware/drivers/ifs/irp-mj-create-mailslot) operation, [FLT_PARAMETERS](../fltkernel/ns-fltkernel-_flt_parameters.md) is a *CreateMailslot* structure, and *CreateMailslot.Parameters* points to a MAILSLOT_CREATE_PARAMETERS structure that describes the mailslot to create or open.

## -see-also

[FLT_PARAMETERS](../fltkernel/ns-fltkernel-_flt_parameters.md)

[IRP_MJ_CREATE_MAILSLOT](/windows-hardware/drivers/ifs/irp-mj-create-mailslot)

