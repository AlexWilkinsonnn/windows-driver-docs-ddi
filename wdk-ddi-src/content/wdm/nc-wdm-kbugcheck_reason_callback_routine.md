---
UID: NC:wdm.KBUGCHECK_REASON_CALLBACK_ROUTINE
title: KBUGCHECK_REASON_CALLBACK_ROUTINE (wdm.h)
description: Driver-implemented callback functions that the system executes when it issues a bug check.
old-location: kernel\bugcheckaddpagescallback.htm
tech.root: kernel
ms.assetid: a3d33a3a-efe7-4346-82bc-555c57ae7b74
ms.date: 05/02/2019
ms.keywords: BugCheckAddPagesCallback, BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, DrvrRtns_337f5b60-9ed5-4a1b-a215-1d3b1e3abb1e.xml, KBUGCHECK_REASON_CALLBACK_ROUTINE, KBUGCHECK_REASON_CALLBACK_ROUTINE callback, MyBugCheckCallback, MyBugCheckCallback callback function [Kernel-Mode Driver Architecture], kernel.bugcheckaddpagescallback, wdm/MyBugCheckCallback
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows Server 2008.
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
req.irql: Called at HIGH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- MyBugCheckCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KBUGCHECK_REASON_CALLBACK_ROUTINE callback function

## -description

Driver-implemented callback functions that the system executes when it issues a bug check.

The <i>KbCallbackAddPages</i> routine adds one or more pages of data to the crash dump file when the operating system issues a bug check.

The <i>KbCallbackDumpIo</i> routine is executed each time the system writes data to a crash dump file.

The <i>KbCallbackSecondaryDumpData</i> routine provides data to the system to append to the crash dump file when the system issues a bug check.

## -parameters

### -param Reason [in]

Specifies the reason for the call to the callback routine. This value can be one of the following as defined in  <a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a>


### -param Record [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a> structure that the driver supplied when it registered this callback. For more information, see the description of the <i>CallbackRecord</i> parameter in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>.

### -param ReasonSpecificData [in, out]

Pointer to a buffer that contains a structure of type determined by the table below. Certain members of this structure are filled in by the operating system before it calls the callback routine, and other members must be filled in by the callback routine. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

|Value|Data Structure|
|--- |--- |
|**KbCallbackSecondaryDumpData**|[**KBUGCHECK_SECONDARY_DUMP_DATA**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_secondary_dump_data)|
|**KbCallbackDumpIo**|[**KBUGCHECK_DUMP_IO**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_dump_io)|
|**KbCallbackAddPages**|[**KBUGCHECK_ADD_PAGES**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_add_pages)|
|**KbCallbackSecondaryMultiPartDumpData**|[**KBUGCHECK_SECONDARY_DUMP_DATA_EX**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_secondary_dump_data_ex)|
|**KbCallbackRemovePages**|[**KBUGCHECK_REMOVE_PAGES**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_remove_pages)|
|**KbCallbackTriageDumpData**|[**KBUGCHECK_TRIAGE_DUMP_DATA**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_triage_dump_data)|

### -param ReasonSpecificDataLength [in]

Specifies the size, in bytes, of the buffer that the <i>ReasonSpecificData</i> parameter points to. 


## -returns

None.

## -remarks

For information about how to implement this callback routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551839">KBUGCHECK_ADD_PAGES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553110">KeRegisterBugCheckReasonCallback</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552003">KeDeregisterBugCheckReasonCallback</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.
