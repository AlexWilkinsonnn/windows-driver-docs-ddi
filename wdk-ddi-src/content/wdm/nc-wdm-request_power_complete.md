---
UID: NC:wdm.REQUEST_POWER_COMPLETE
title: REQUEST_POWER_COMPLETE (wdm.h)
description: The PowerCompletion callback routine completes the processing of a power IRP.
old-location: kernel\powercompletion.htm
tech.root: kernel
ms.assetid: 2272790e-324a-4bd4-86ed-b76305a2940b
ms.date: 04/30/2018
ms.keywords: PowerCompletion, PowerCompletion routine [Kernel-Mode Driver Architecture], REQUEST_POWER_COMPLETE, kernel.powercompletion, wdm/PowerCompletion
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 2000 and later versions of Windows.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL (see Remarks section).
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	PowerCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# REQUEST_POWER_COMPLETE callback function


## -description


The <i>PowerCompletion</i> callback routine completes the processing of a power IRP.


## -parameters




### -param DeviceObject [in]

A pointer to the target <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> for the completed power IRP.


### -param MinorFunction [in]

Specifies the minor function code in the power IRP. For more information, see the list of supported <b>IRP_MN_<i>XXX</i></b> codes in the Remarks section.


### -param PowerState [in]

Specifies the <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> or <a href="https://msdn.microsoft.com/bb30bc89-d1f2-4cb3-bcfb-fb76c69dba27">system power state</a> that was passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559734">PoRequestPowerIrp</a> routine.


### -param Context [in, optional]

A pointer to the context that was passed to <b>PoRequestPowerIrp</b>.


### -param IoStatus [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure for the completed IRP.


## -returns



None




## -remarks



A driver that sends a power IRP might need to perform additional tasks after all other drivers have completed the IRP. If so, the sending driver should register a <i>PowerCompletion</i> callback routine during the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559734">PoRequestPowerIrp</a> routine that allocates the IRP.

A driver's <i>PowerCompletion</i> callback routine is used only for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a> IRPs that have minor IRP codes of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563731">Sending IRP_MN_QUERY_POWER or IRP_MN_SET_POWER for Device Power States</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565599">Wait/Wake Callback Routines</a>.

The I/O manager calls the sending driver's <i>PowerCompletion</i> routine only after the I/O manager has called all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routines that were set by other drivers as they passed the IRP down the stack. The <i>PowerCompletion</i> routine performs any additional tasks that the sender of the IRP requires after all other drivers have completed the IRP. The <i>PowerCompletion</i> routine should not free the IRP—the power manager does that.

In Windows 2000 and later versions of Windows, the <i>PowerCompletion</i> routine is called at IRQL = PASSIVE_LEVEL or IRQL = DISPATCH_LEVEL. In Windows 98/Me, the <i>PowerCompletion</i> routine is always called at IRQL = PASSIVE_LEVEL, and drivers must complete IRPs at IRQL = PASSIVE_LEVEL.



#### Examples

To define a <i>PowerCompletion</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>PowerCompletion</i> callback routine that is named <code>MyPowerCompletion</code>, use the REQUEST_POWER_COMPLETE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>REQUEST_POWER_COMPLETE MyPowerCompletion;</pre>
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
  MyPowerCompletion(
    PDEVICE_OBJECT DeviceObject,
    UCHAR MinorFunction,
    POWER_STATE PowerState,
    PVOID Context,
    PIO_STATUS_BLOCK IoStatus
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The REQUEST_POWER_COMPLETE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the REQUEST_POWER_COMPLETE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559734">PoRequestPowerIrp</a>
 

 

