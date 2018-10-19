---
UID: NF:wdfinterrupt.WdfInterruptSetPolicy
title: WdfInterruptSetPolicy function
author: windows-driver-content
description: The WdfInterruptSetPolicy method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.
old-location: wdf\wdfinterruptsetpolicy.htm
tech.root: wdf
ms.assetid: f61bef13-d9b5-4e6a-8657-995a1fcbf7b1
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_86b7a562-3aee-4c0b-9a68-f98a2b76588f.xml, WdfInterruptSetPolicy, WdfInterruptSetPolicy method, kmdf.wdfinterruptsetpolicy, wdf.wdfinterruptsetpolicy, wdfinterrupt/WdfInterruptSetPolicy
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfInterruptSetPolicy
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptSetPolicy function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptSetPolicy</b> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param Policy [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/Ff552354">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.


### -param Priority [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552355">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.


### -param TargetProcessorSet [in]

A [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)-typed value that specifies a processor affinity for the interrupt, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Windows Vista and later versions of the operating system allow drivers to specify an interrupt's priority, processor affinity, and affinity policy. For information about how to use the registry to override the values that <b>WdfInterruptSetPolicy</b> sets, see <a href="https://msdn.microsoft.com/e36a52d0-3a94-4017-b4a1-0b41f737523c">Interrupt Affinity and Priority</a>.

If a driver is running on an operating system version that is earlier than Windows Vista, the framework ignores the values that the driver specifies when it calls <b>WdfInterruptSetPolicy</b>.

For more information about registry values and INF sections that specify an interrupt's priority, processor affinity, and affinity policy, see <a href="https://msdn.microsoft.com/e36a52d0-3a94-4017-b4a1-0b41f737523c">Interrupt Affinity and Priority</a>.

If a driver calls <b>WdfInterruptSetPolicy</b>, it typically does so in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function, after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.

If your driver creates interrupts in <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>, do not use <b>WdfInterruptSetPolicy</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547381">WdfInterruptSetExtendedPolicy</a>. Instead, apply policy in <a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a>, by directly manipulating the interrupt resource requirement that this callback function receives in its <i>IoResourceRequirementsList</i> parameter.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example assigns a device interrupt to processor 0, with normal priority.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define AFFINITY_MASK(n) ((ULONG_PTR)1 &lt;&lt; (n))

WdfInterruptSetPolicy(
                      Interrupt,
                      WdfIrqPolicySpecifiedProcessors,
                      WdfIrqPriorityNormal,
                      AFFINITY_MASK(0)
                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547381">WdfInterruptSetExtendedPolicy</a>
 

 

