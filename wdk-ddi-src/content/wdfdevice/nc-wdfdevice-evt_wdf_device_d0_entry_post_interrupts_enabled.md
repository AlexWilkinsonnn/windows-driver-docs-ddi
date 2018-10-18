---
UID: NC:wdfdevice.EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED
title: EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED
author: windows-driver-content
description: A driver's EvtDeviceD0EntryPostInterruptsEnabled event callback function performs device-specific operations that are required after the driver has enabled the device's hardware interrupts.
old-location: wdf\evtdeviced0entrypostinterruptsenabled.htm
tech.root: wdf
ms.assetid: 38d74ce1-9d9d-4da5-a2b3-579048850b28
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e37cc70a-3e3e-4268-afda-8b802cc72461.xml, EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED, EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED callback, EvtDeviceD0EntryPostInterruptsEnabled, EvtDeviceD0EntryPostInterruptsEnabled callback function, kmdf.evtdeviced0entrypostinterruptsenabled, wdf.evtdeviced0entrypostinterruptsenabled, wdfdevice/EvtDeviceD0EntryPostInterruptsEnabled
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceD0EntryPostInterruptsEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceD0EntryPostInterruptsEnabled</i> event callback function performs device-specific operations that are required after the driver has enabled the device's hardware interrupts.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PreviousState [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552421">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the previous device power state.


## -returns



If the <i>EvtDeviceD0EntryPostInterruptsEnabled</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



To register an <i>EvtDeviceD0EntryPostInterruptsEnabled</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546135">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The <i>EvtDeviceD0EntryPostInterruptsEnabled</i> callback function is called at IRQL = PASSIVE_LEVEL, after the driver's <a href="https://msdn.microsoft.com/981195e6-6f62-4a6f-9c84-d98f6cd7bab3">EvtInterruptEnable</a> callback function returns. A driver can provide this function if it must perform device-specific operations after it has enabled an interrupt, if those operations should not be performed at IRQL = DIRQL in the <i>EvtInterruptEnable</i> callback function. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about handling interrupts, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtDeviceD0EntryPostInterruptsEnabled</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceD0EntryPostInterruptsEnabled</i> callback function that is named <i>MyDeviceD0EntryPostInterruptsEnabled</i>, use the <b>EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED  MyDeviceD0EntryPostInterruptsEnabled;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyDeviceD0EntryPostInterruptsEnabled(
    WDFDEVICE  Device,
    WDF_POWER_DEVICE_STATE  PreviousState
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_D0_ENTRY_POST_INTERRUPTS_ENABLED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/8f57c3b3-2dcf-44a3-a3c2-c9585bdfa253">EvtDeviceD0ExitPreInterruptsDisabled</a>
 

 

