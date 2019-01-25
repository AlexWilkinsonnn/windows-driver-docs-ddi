---
UID: NC:wdm.KBUGCHECK_CALLBACK_ROUTINE
title: KBUGCHECK_CALLBACK_ROUTINE (wdm.h)
description: The BugCheckCallback routine is executed whenever the system issues a bug check.
old-location: kernel\bugcheckcallback.htm
tech.root: kernel
ms.assetid: ecd777f0-bba2-4f14-9fa6-8f47ac83fe7f
ms.date: 04/30/2018
ms.keywords: BugCheckCallback, BugCheckCallback routine [Kernel-Mode Driver Architecture], DrvrRtns_e968f3db-9875-4f94-8781-074029354e2c.xml, KBUGCHECK_CALLBACK_ROUTINE, kernel.bugcheckcallback, wdm/BugCheckCallback
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: Called at HIGH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	BugCheckCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KBUGCHECK_CALLBACK_ROUTINE callback function


## -description


The <i>BugCheckCallback</i> routine is executed whenever the system issues a bug check.


## -parameters




### -param Buffer [in]

A pointer to the buffer that was specified when the callback was registered.


### -param Length [in]

Specifies the length, in bytes, of the buffer that is pointed to by the <i>Buffer</i> parameter.


## -returns



None




## -remarks



Drivers can supply a <i>BugCheckCallback</i> that resets the device to a known state if the system issues a bug check.

Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a> to register a <i>BugCheckCallback</i> routine. A driver can subsequently remove the callback by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551992">KeDeregisterBugCheckCallback</a> routine. If the driver can be unloaded, it must remove any registered callbacks in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

A <i>BugCheckCallback</i> routine is strongly restricted in the actions it can take. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>. The routine <u>can</u> safely use the <b>READ_PORT_<i>XXX</i></b>, <b>READ_REGISTER_<i>XXX</i></b>, <b>WRITE_PORT_<i>XXX</i></b>, and <b>WRITE_REGISTER_<i>XXX</i></b> routines to interact with the device.

Drivers that require more sophisticated interaction with the system as it issues a bug check can instead implement <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> routines.

Note that beginning with the Windows XP SP1 and Windows Server 2003 operating systems, <i>BugCheckCallback</i> routines execute after the system crash dump file has already been written. (On earlier versions of Windows, the routines execute <u>before</u> the crash dump file is written.) Thus, any data that is stored in the buffer specified by the <i>Buffer</i> parameter will not appear in the crash dump file. Drivers that are required to write data to the crash dump file instead implement a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> routine. (On earlier versions of Windows, the data written to <i>Buffer</i> does appear in the crash dump file.) 


#### Examples

To define a <i>BugCheckCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>BugCheckCallback</i> callback routine that is named <code>MyBugCheckCallback</code>, use the KBUGCHECK_CALLBACK_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KBUGCHECK_CALLBACK_ROUTINE MyBugCheckCallback;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyBugCheckCallback(
    PVOID  Buffer,
    ULONG  Length
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The KBUGCHECK_CALLBACK_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KBUGCHECK_CALLBACK_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551992">KeDeregisterBugCheckCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>
 

 

