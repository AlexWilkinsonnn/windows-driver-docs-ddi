---
UID: NF:ks.KsAddItemToObjectBag
title: KsAddItemToObjectBag function (ks.h)
description: The KsAddItemToObjectBag function adds an object or block of memory to the given object bag.
old-location: stream\ksadditemtoobjectbag.htm
tech.root: stream
ms.assetid: 4c8b6252-8438-4cd1-81e0-02c260da0daf
ms.date: 04/23/2018
ms.keywords: KsAddItemToObjectBag, KsAddItemToObjectBag function [Streaming Media Devices], avfunc_c7496331-05a5-4336-9c62-144e2db6e218.xml, ks/KsAddItemToObjectBag, stream.ksadditemtoobjectbag
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAddItemToObjectBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAddItemToObjectBag function


## -description


The<b> KsAddItemToObjectBag</b> function adds an object or block of memory to the given object bag. 


## -parameters




### -param ObjectBag [in]

The KSOBJECT_BAG (equivalent to type PVOID) to which to add the requested item. Every AVStream object (for example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>) contains a member called <i>Bag</i>. Pass that member in this parameter.


### -param Item [in]

A pointer to the item to add to the object bag.


### -param Free [in, optional]

A function that is called when the item is removed from the object bag or when the object bag is deleted. This function typically is used to free any dynamic memory associated with <i>Item</i>. The function should be prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void Free (IN PVOID Data);</pre>
</td>
</tr>
</table></span></div>
If the caller does not specify this optional parameter, <i>Item</i> is freed with <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> when removed from the object bag or when the object bag is deleted.


## -returns



Either returns STATUS_SUCCESS indicating that the addition went normally or STATUS_INSUFFICIENT_RESOURCES indicating that there are insufficient system resources for the operation to proceed.




## -remarks



Before calling <b>KsAddItemToObjectBag</b>, the minidriver must acquire the mutex associated with the specific object bag. If <i>ObjectBag</i> is a member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>, acquire the device mutex. If the bag is a member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>, acquire the filter control mutex. If the bag is a member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> object, acquire the parent KSFILTER's filter control mutex.

For more information, see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560965">KsAllocateObjectBag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561031">KsCopyObjectBagItems</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561695">KsDiscard</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562562">KsFreeObjectBag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566798">KsRemoveItemFromObjectBag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568796">_KsEdit</a>
 

 

