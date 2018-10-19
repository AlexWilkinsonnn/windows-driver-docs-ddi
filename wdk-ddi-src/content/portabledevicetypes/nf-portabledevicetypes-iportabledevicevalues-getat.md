---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetAt
title: IPortableDeviceValues::GetAt
author: windows-driver-content
description: Retrieves a value from the collection, by a zero-based index.
old-location: wpddk\iportabledevicevalues_getat.htm
tech.root: wpd_dk
ms.assetid: 887aab56-2f3f-4aaa-96fa-c597bc540a92
ms.date: 02/15/2018
ms.keywords: GetAt, GetAt method, GetAt method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetAt method, IPortableDeviceValues.GetAt, IPortableDeviceValues::GetAt, IPortableDeviceValuesGetAt, portabledevicetypes/IPortableDeviceValues::GetAt, wpddk.iportabledevicevalues_getat
ms.topic: method
req.header: portabledevicetypes.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	PortableDeviceTypes.h
api_name:
-	IPortableDeviceValues.GetAt
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::GetAt


## -description



Retrieves a value from the collection, by a zero-based index.




## -parameters




### -param index [in]

A <b>DWORD</b> that specifies a zero-based index in the collection.


### -param pKey [in, out]

An optional <b>PROPERTYKEY</b> pointer that retrieves the key of the specified item.


### -param pValue [in, out]

An optional <b>PROPVARIANT</b> that retrieves the value of the specified item. The caller must free the memory by calling <b>PropVariantClear</b> when done with it.


## -returns



The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
An invalid index number was specified.

</td>
</tr>
</table>
 




## -remarks



If a property indicates a value of type VT_UNKNOWN, the property will be one of the Windows Portable Devices interfaces (<a href="https://msdn.microsoft.com/library/windows/hardware/ff597583">IPortableDeviceKeyCollection</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff597589">IPortableDevicePropVariantCollection</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff597597">IPortableDeviceValues</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff597598">IPortableDeviceValuesCollection</a>). No other interfaces can be returned by Windows Portable Devices.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/6c63adae-ab57-4826-aaa2-6953ab918ddd">IPortableDeviceValues::GetStringValue</a>
 

 

