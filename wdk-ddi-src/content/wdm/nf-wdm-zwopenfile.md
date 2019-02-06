---
UID: NF:wdm.ZwOpenFile
title: ZwOpenFile function (wdm.h)
description: The ZwOpenFile routine opens an existing file, directory, device, or volume.
old-location: kernel\zwopenfile.htm
tech.root: kernel
ms.assetid: 7c07d250-6287-4dd3-96f9-f301bad8b6f3
ms.date: 04/30/2018
ms.keywords: NtOpenFile, ZwOpenFile, ZwOpenFile routine [Kernel-Mode Driver Architecture], k111_efde7b0f-a00d-47c8-8a34-ae22fb909718.xml, kernel.zwopenfile, wdm/NtOpenFile, wdm/ZwOpenFile
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwOpenFile
-	NtOpenFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwOpenFile function


## -description


The <b>ZwOpenFile</b> routine opens an existing file, directory, device, or volume.


## -parameters




### -param FileHandle [out]

Pointer to a HANDLE variable that receives a handle to the file.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>.


### -param ObjectAttributes [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


### -param IoStatusBlock [out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation.


### -param ShareAccess [in]

Specifies the type of share access for the file. For more information, see the <i>ShareAccess</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>.


### -param OpenOptions [in]

Specifies the options to apply when opening the file. For more information, see the <i>CreateOptions</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>.


## -returns



<b>ZwOpenFile</b> returns STATUS_SUCCESS or the appropriate NTSTATUS error code. In the latter case, the caller can find more information about the cause of the failure by checking the <i>IoStatusBlock</i> parameter.




## -remarks



<b>ZwOpenFile</b> supplies a handle that the caller can use to manipulate a file's data, or the file object's state and attributes. <b>ZwOpenFile</b> provides a subset of the functionality provided by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565384">Using Files in a Driver</a>.

Once the handle pointed to by <i>FileHandle</i> is no longer in use, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>. 

Callers of <b>ZwOpenFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtOpenFile</b>" instead of "<b>ZwOpenFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>
 

 

