---
UID: NE:wdm._KBUGCHECK_CALLBACK_REASON
title: _KBUGCHECK_CALLBACK_REASON (wdm.h)
description: The KBUGCHECK_CALLBACK_REASON enumeration type specifies the situations in which a bug-check callback executes.
old-location: kernel\kbugcheck_callback_reason.htm
tech.root: kernel
ms.assetid: 08246843-9b6e-4694-8475-acb02fbdd82b
ms.date: 04/30/2018
ms.keywords: KBUGCHECK_CALLBACK_REASON, KBUGCHECK_CALLBACK_REASON enumeration [Kernel-Mode Driver Architecture], KbCallbackAddPages, KbCallbackDumpIo, KbCallbackInvalid, KbCallbackReserved1, KbCallbackSecondaryDumpData, _KBUGCHECK_CALLBACK_REASON, kernel.kbugcheck_callback_reason, sysenum_e8373f57-7ba5-44ad-9ad9-4110710732ee.xml, wdm/KBUGCHECK_CALLBACK_REASON, wdm/KbCallbackAddPages, wdm/KbCallbackDumpIo, wdm/KbCallbackInvalid, wdm/KbCallbackReserved1, wdm/KbCallbackSecondaryDumpData
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- KBUGCHECK_CALLBACK_REASON
product:
- Windows
targetos: Windows
req.typenames: KBUGCHECK_CALLBACK_REASON
---

# _KBUGCHECK_CALLBACK_REASON enumeration


## -description


The <b>KBUGCHECK_CALLBACK_REASON</b> enumeration type specifies the situations in which a bug-check callback executes.


## -enum-fields




### -field KbCallbackInvalid

Reserved for system use. Do not use.


### -field KbCallbackReserved1

Reserved for system use. Do not use.


### -field KbCallbackSecondaryDumpData

Specifies that the callback is executed to provide data that the system appends to the secondary section of the crash dump file. For more information about this type of callback, see "Implementing KbCallbackSecondaryDumpData Callback Routine" in <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.


### -field KbCallbackDumpIo

Specifies that the callback is executed each time a section of the dump file is written. For more information about this type of callback, see "Implementing KbCallbackDumpIo Callback Routine" in <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.


### -field KbCallbackAddPages

Specifies that the callback is executed to provide one or more pages of data that the system adds to the primary section of the crash dump file. For more information about this type of callback, see "Implementing KbCallbackAddPages Callback Routine" in <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>. This enumeration value is supported in Windows Server 2008 and later versions of Windows.


### -field KbCallbackSecondaryMultiPartDumpData

Specifies that the callback is executed to get the amount of data the driver wants to store in the dump file. This enumeration value is supported in Windows Server 2008 and later versions of Windows.

### -field KbCallbackRemovePages


### -field KbCallbackTriageDumpData

## Remarks

For information about how this enumeration is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553110">KeRegisterBugCheckReasonCallback</a>
