---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetIPortableDeviceValuesValue
title: IPortableDeviceValues::GetIPortableDeviceValuesValue (portabledevicetypes.h)
description: Retrieves an IPortableDeviceValues value (type VT_UNKNOWN) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getiportabledevicevaluesvalue.htm
tech.root: wpd_dk
ms.assetid: f0ec918d-57a2-40a4-b7ca-878484fc46ac
ms.date: 02/15/2018
ms.keywords: GetIPortableDeviceValuesValue, GetIPortableDeviceValuesValue method, GetIPortableDeviceValuesValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetIPortableDeviceValuesValue method, IPortableDeviceValues.GetIPortableDeviceValuesValue, IPortableDeviceValues::GetIPortableDeviceValuesValue, IPortableDeviceValuesGetIPortableDeviceValuesValue, portabledevicetypes/IPortableDeviceValues::GetIPortableDeviceValuesValue, wpddk.iportabledevicevalues_getiportabledevicevaluesvalue
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
-	IPortableDeviceValues.GetIPortableDeviceValuesValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetIPortableDeviceValuesValue


## -description



Retrieves an <b>IPortableDeviceValues</b> value (type VT_UNKNOWN) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param ppValue [out]

Address of a variable that receives a pointer to the retrieved <a href="https://msdn.microsoft.com/library/windows/hardware/ff597597">IPortableDeviceValues</a> interface. The caller is responsible for calling <b>Release</b> on the retrieved interface.


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
<dt><b>DISP_E_TYPEMISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not an <b>IPortableDeviceValues</b> interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/2ab54174-9e1b-4b52-894c-489d67b7f1be">IPortableDeviceValues::SetIPortableDeviceValuesValue</a>
 

 

