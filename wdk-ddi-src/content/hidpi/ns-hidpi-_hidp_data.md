---
UID: NS:hidpi._HIDP_DATA
title: "_HIDP_DATA" (hidpi.h)
description: The HIDP_DATA structure contains information about a HID control's data index and value in a HID report.
old-location: hid\hidp_data.htm
tech.root: hid
ms.assetid: f48bbf84-027f-4579-b83c-7dfb1cbe6b65
ms.date: 04/30/2018
ms.keywords: "*PHIDP_DATA, HIDP_DATA, HIDP_DATA structure [Human Input Devices], PHIDP_DATA, PHIDP_DATA structure pointer [Human Input Devices], _HIDP_DATA, hid.hidp_data, hidpi/HIDP_DATA, hidpi/PHIDP_DATA, hidstrct_690e0e92-9de7-44e0-8550-4f84d7bb768e.xml"
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
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
-	HeaderDef
api_location:
-	hidpi.h
api_name:
-	HIDP_DATA
product:
- Windows
targetos: Windows
req.typenames: HIDP_DATA, *PHIDP_DATA
---

# _HIDP_DATA structure


## -description


The HIDP_DATA structure contains information about a HID control's <a href="https://msdn.microsoft.com/84577544-515a-4fdc-86e5-518182c6c461">data index</a> and value in a HID report.


## -struct-fields




### -field DataIndex

Specifies the data index of a control.


### -field Reserved

Reserved for internal system use only.


### -field RawValue

Contains the binary data extracted from a report if the control is a value.


### -field On

Specifies, if <b>TRUE</b> and the control is a button, that the button is set to ON (1). Otherwise, if <b>On</b> is <b>FALSE</b> and the control is a button, the button is set to OFF (zero).


## -remarks



See <a href="https://msdn.microsoft.com/d26d169f-4116-4d81-94c7-63c92d22877d">Extracting and Setting Control Data by Data Indices</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539718">HidP_GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539783">HidP_SetData</a>
 

 

