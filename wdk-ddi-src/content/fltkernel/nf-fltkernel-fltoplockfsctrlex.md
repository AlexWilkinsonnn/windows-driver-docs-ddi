---
UID: NF:fltkernel.FltOplockFsctrlEx
title: FltOplockFsctrlEx function
author: windows-driver-content
description: The FltOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver.
old-location: ifsk\fltoplockfsctrlex.htm
tech.root: ifsk
ms.assetid: 02adb7a7-0c1d-4dd4-bde2-f2e700a7ee76
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_fbf1fd08-c50d-41f9-8d13-5bd8f1265625.xml, FltOplockFsctrlEx, FltOplockFsctrlEx routine [Installable File System Drivers], fltkernel/FltOplockFsctrlEx, ifsk.fltoplockfsctrlex
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows 8.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltOplockFsctrlEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltOplockFsctrlEx function


## -description


The <b>FltOplockFsctrlEx</b> routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver. 


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>. 


### -param CallbackData [in]

A pointer to the callback data structure for the I/O operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). This parameter is required and cannot be <b>NULL</b>. 


### -param OpenCount [in]

The number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Oplock Semantics Overview</a>. 


### -param Flags [in]

A bitmask for the associated oplock operations. A minifilter driver sets bits to specify the behavior of <b>FltOplockFsctrlEx</b>. The <i>Flags</i> parameter has the following options:





#### OPLOCK_FSCTRL_FLAG_ALL_KEYS_MATCH (0x00000001)

Specifies that the file system verified that all oplock keys on any handles that are currently open match. By specifying this flag, you allow the oplock package to grant an oplock of level RW or RWH when more than one open handle to the file exists. For more information about oplock types, see the Oplock Semantics <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Overview</a> page. 


## -returns



<b>FltOplockFsctrlEx</b> returns FLT_PREOP_PENDING for some FSCTL operations. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. Otherwise, <b>FltOplockFsctrlEx</b> returns FLT_PREOP_COMPLETE. 




## -remarks



A minifilter driver calls <b>FltOplockFsctrlEx</b> to perform various opportunistic lock operations for a create operation or file system control I/O operation. The FLT_CALLBACK_DATA structure pointed to by the <i>CallbackData</i> parameter must represent an IRP-based <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> operation. 

If the operation is an IRP_MJ_FILE_SYSTEM_CONTROL operation, you can use <b>FltOplockFsctrlEx</b> with the following FSCTL codes: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545530">FSCTL_REQUEST_OPLOCK</a>


The FSCTL code is set in the <b>FsControlCode</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544673">FLT_PARAMETERS</a> structure for the operation. For more information about <b>FsControlCode</b> and other IRP_MJ_FILE_SYSTEM_CONTROL parameters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>. 

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

If the operation is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request, you can use <b>FltOplockFsctrlEx</b>  to request a pending filter opportunistic lock if all of the following conditions are true: 

<ul>
<li>
The value of the <i>OpenCount</i> parameter is 1. 

</li>
<li>
The value of the <i>DesiredAccess</i> parameter for the IRP_MJ_CREATE request is FILE_READ_ATTRIBUTES. This parameter is set in the <b>SecurityContext</b> member of the FLT_PARAMETERS structure for the operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544687">FLT_PARAMETERS for IRP_MJ_CREATE</a>. 

</li>
<li>
The value of the <i>ShareAccess</i> parameter for the IRP_MJ_CREATE operation is FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE. This parameter is set in the <b>ShareAccess</b> member of the FLT_PARAMETERS structure for the operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544687">FLT_PARAMETERS for IRP_MJ_CREATE</a>. 

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544687">FLT_PARAMETERS for IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545530">FSCTL_REQUEST_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547113">FsRtlOplockFsctrlEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>
 

 

