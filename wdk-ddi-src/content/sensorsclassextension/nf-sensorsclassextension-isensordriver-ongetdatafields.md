---
UID: NF:sensorsclassextension.ISensorDriver.OnGetDataFields
title: ISensorDriver::OnGetDataFields
author: windows-driver-content
description: The ISensorDriver::OnGetDataFields method retrieves current sensor data.
old-location: sensors\isensordriver_ongetdatafields.htm
tech.root: sensors
ms.assetid: a9233a0f-ac80-46be-9abe-7b87d25736f9
ms.date: 5/3/2018
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetDataFields method, ISensorDriver.OnGetDataFields, ISensorDriver::OnGetDataFields, OnGetDataFields, OnGetDataFields method [Sensor Devices], OnGetDataFields method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetdatafields, sensorsclassextension/ISensorDriver::OnGetDataFields
ms.topic: method
req.header: sensorsclassextension.h
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
api_name:
-	OnGetDataFields
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorDriver::OnGetDataFields


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545607">ISensorDriver::OnGetDataFields</a> method retrieves current sensor data.


## -parameters




### -param pClientFile

 Pointer to an IWDFFile interface that represents the file object for the application requesting the data.


### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting data.


### -param pDataFields

Pointer to an IPortableDeviceKeyCollection that contains the list of PROPERTYKEY values that represent the data fields being requested. 


### -param ppDataValues

Address of an IPortableDeviceValues pointer that receives the requested data.


## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

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
<dt><b>HRESULT_FROM_WIN32(ERROR_NO_DATA)</b></dt>
</dl>
</td>
<td width="60%">
The sensor has no data to report. Each of the data fields returned in the <i>ppDataValues</i> parameter is VT_EMPTY.

</td>
</tr>
</table>
 




## -remarks



Data fields contain sensor-generated data, as opposed to properties, which describe the sensor device. Platform-defined data fields are defined in sensors.h.

Each <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> object returned by this method must contain a time stamp, as described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545725">SENSOR_CATEGORY_ALL</a>. 

The sensor class extension is responsibile for freeing any <b>PROPVARIANT</b> structures returned by this method.

The sensor class extension calls this method only for sensors for which the user has granted permission through Control Panel.

<a href="http://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> are documented in Windows Portable Devices.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545566">ISensorDriver</a>
 

 

