---
UID: NF:wdfinterrupt.WdfInterruptSetExtendedPolicy
title: WdfInterruptSetExtendedPolicy function (wdfinterrupt.h)
description: The WdfInterruptSetExtendedPolicy method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
old-location: wdf\wdfinterruptsetextendedpolicy.htm
tech.root: wdf
ms.assetid: 043c15dc-ebd7-4d91-8f65-d89d6064cc7c
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_ed600fb0-0e09-4c00-a132-cd4947dd2b04.xml, WdfInterruptSetExtendedPolicy, WdfInterruptSetExtendedPolicy method, kmdf.wdfinterruptsetextendedpolicy, wdf.wdfinterruptsetextendedpolicy, wdfinterrupt/WdfInterruptSetExtendedPolicy
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfInterruptSetExtendedPolicy
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptSetExtendedPolicy function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptSetExtendedPolicy</b> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param PolicyAndGroup [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure that the caller allocates and initializes.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Windows Vista and later versions of the operating system allow drivers to use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547387">WdfInterruptSetPolicy</a> method to specify an interrupt's priority, processor affinity, and affinity policy. In addition, versions 1.9 and later of KMDF allow drivers to use the <b>WdfInterruptSetExtendedPolicy</b> method to specify an interrupt's priority, processor affinity, affinity policy, and processor group.

For information about how to use the registry to override the values that <b>WdfInterruptSetExtendedPolicy</b> sets, see <a href="https://msdn.microsoft.com/e36a52d0-3a94-4017-b4a1-0b41f737523c">Interrupt Affinity and Priority</a>.

If a driver is running on an operating system version that is earlier than Windows 7, the framework ignores the value that the driver specifies for the processor group number when it calls <b>WdfInterruptSetExtendedPolicy</b>.

If a driver is running on an operating system version that is earlier than Windows Vista, the framework ignores all values that the driver specifies when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547387">WdfInterruptSetPolicy</a> or <b>WdfInterruptSetExtendedPolicy</b>.

For more information about registry values and INF sections that specify an interrupt's priority, processor affinity, and affinity policy, see <a href="https://msdn.microsoft.com/e36a52d0-3a94-4017-b4a1-0b41f737523c">Interrupt Affinity and Priority</a>.

If a driver calls <b>WdfInterruptSetExtendedPolicy</b>, it typically does so in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function, after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.

If your driver creates interrupts in <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>, do not use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547387">WdfInterruptSetPolicy</a> or <b>WdfInterruptSetExtendedPolicy</b>. Instead, you can instead apply policy in <a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a>, by directly manipulating the interrupt resource requirement that this callback function receives in its <i>IoResourceRequirementsList</i> parameter.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552350">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552349">WDF_INTERRUPT_EXTENDED_POLICY</a> structure; sets values for the policy, priority, and target processor set; and calls <b>WdfInterruptSetExtendedPolicy</b>. The example sets normal priority for the interrupt and assigns the interrupt to processor 0 in processor group 2. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define AFFINITY_MASK(n) ((ULONG_PTR)1 &lt;&lt; (n))

WDF_INTERRUPT_EXTENDED_POLICY myExtendedPolicy;

WDF_INTERRUPT_EXTENDED_POLICY_INIT(&myExtendedPolicy);
myExtendedPolicy.Policy = WdfIrqPolicySpecifiedProcessors;
myExtendedPolicy.Priority = WdfIrqPriorityNormal;
myExtendedPolicy.TargetProcessorSetAndGroup.Mask = AFFINITY_MASK(0);
myExtendedPolicy.TargetProcessorSetAndGroup.Group = 2;

WdfInterruptSetExtendedPolicy(
                              Interrupt,
                              &myExtendedPolicy
 );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547387">WdfInterruptSetPolicy</a>
 

 

