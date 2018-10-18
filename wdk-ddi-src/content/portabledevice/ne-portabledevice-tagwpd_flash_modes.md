---
UID: NE:portabledevice.tagWPD_FLASH_MODES
title: tagWPD_FLASH_MODES
author: windows-driver-content
description: The WPD_FLASH_MODES enumeration type describes a flash mode to use when capturing images with a device.
old-location: wpddk\wpd_flash_modes.htm
tech.root: wpd_dk
ms.assetid: 31aa00d6-bbf8-47ae-bbc6-eeecfb542c3f
ms.date: 2/15/2018
ms.keywords: WPD_FLASH_MODES, WPD_FLASH_MODES enumeration, WPD_FLASH_MODE_AUTO, WPD_FLASH_MODE_EXTERNAL_SYNC, WPD_FLASH_MODE_FILL, WPD_FLASH_MODE_OFF, WPD_FLASH_MODE_RED_EYE_AUTO, WPD_FLASH_MODE_RED_EYE_FILL, WPD_FLASH_MODE_UNDEFINED, enumeration, portabledevice/WPD_FLASH_MODES, portabledevice/WPD_FLASH_MODE_AUTO, portabledevice/WPD_FLASH_MODE_EXTERNAL_SYNC, portabledevice/WPD_FLASH_MODE_FILL, portabledevice/WPD_FLASH_MODE_OFF, portabledevice/WPD_FLASH_MODE_RED_EYE_AUTO, portabledevice/WPD_FLASH_MODE_RED_EYE_FILL, portabledevice/WPD_FLASH_MODE_UNDEFINED, tagWPD_FLASH_MODES, wpddk.wpd_flash_modes
ms.topic: enum
req.header: portabledevice.h
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
-	HeaderDef
api_location:
-	PortableDevice.h
api_name:
-	WPD_FLASH_MODES
product:
-	Windows
targetos: Windows
req.typenames: WPD_FLASH_MODES
---

# tagWPD_FLASH_MODES enumeration


## -description



The <b>WPD_FLASH_MODES</b> enumeration type describes a flash mode to use when capturing images with a device.




## -enum-fields




### -field WPD_FLASH_MODE_UNDEFINED

No flash mode has been specified.


### -field WPD_FLASH_MODE_AUTO

Specifies that the flash should be used in the automatic mode, as specified by the device.


### -field WPD_FLASH_MODE_OFF

Specifies that no flash should be used.


### -field WPD_FLASH_MODE_FILL

Specifies a fill-type flash.


### -field WPD_FLASH_MODE_RED_EYE_AUTO

Specifies that the red eye reduction flash should be used.


### -field WPD_FLASH_MODE_RED_EYE_FILL

Specifies that the red eye fill flash should be used.


### -field WPD_FLASH_MODE_EXTERNAL_SYNC

Specifies that the flash should be synchronized with other external flash devices.


## -remarks



This enumeration is used by the <a href="wpd_still_image_properties.htm">WPD_STILL_IMAGE_FLASH_MODE</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597672">Structures and Enumeration Types</a>
 

 

