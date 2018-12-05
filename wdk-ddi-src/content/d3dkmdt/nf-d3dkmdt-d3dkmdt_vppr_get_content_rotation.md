---
UID: NF:d3dkmdt.D3DKMDT_VPPR_GET_CONTENT_ROTATION
title: D3DKMDT_VPPR_GET_CONTENT_ROTATION function
author: windows-driver-content
description: A helper function that extracts the combined rotation that the user sees from the default display orientation from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration.
old-location: display\d3dkmdt_vppr_get_content_rotation.htm
tech.root: display
ms.assetid: 61C1EB2F-E4CF-4B18-AD7B-6B24EF14E71F
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VPPR_GET_CONTENT_ROTATION, D3DKMDT_VPPR_GET_CONTENT_ROTATION function [Display Devices], d3dkmdt/D3DKMDT_VPPR_GET_CONTENT_ROTATION, display.d3dkmdt_vppr_get_content_rotation
ms.topic: function
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION
req.target-min-winversvr: Windows Server 2012 R2
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
-	DllExport
api_location:
-	D3dkmdt.h
api_name:
-	D3DKMDT_VPPR_GET_CONTENT_ROTATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMDT_VPPR_GET_CONTENT_ROTATION function


## -description


A helper function that extracts the combined rotation that the user sees from the default display orientation from a given value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration. This value is effectively the sum of the offset angle and the angle that the Desktop Window Manager (DWM) has already rotated the primary clone path content. Only drivers that support path-independent rotation (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION) should call this function.


## -parameters




### -param Rotation

On input, a value from  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration.

On output, a value between 1 and 4, inclusive, that corresponds to the <b>OFFSET</b> portion of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> constant values. An output value of 1 (identity) represents 0 degrees of total rotation, 2 represents 90 degrees, and so on. An output value of 0 indicates that the VidPN path is not initialized.

The output value of <i>Rotation</i> is the sum of the output values from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn653323">D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn653324">D3DKMDT_VPPR_GET_OFFSET_ROTATION</a> functions minus 1.


## -returns

The returned value corresponds to the rotation and offset angles as follows:

|Input enumeration value|Input enumeration constant|Rotation + offset, in degrees|Output Rotation value|
|--- |--- |--- |--- |
|0|D3DKMDT_VPPR_UNINITIALIZED|-|0|
|1|D3DKMDT_VPPR_IDENTITY|0|1|
|2|D3DKMDT_VPPR_ROTATE90|90|2|
|3|D3DKMDT_VPPR_ROTATE180|180|3|
|4|D3DKMDT_VPPR_ROTATE270|270|4|
|5|D3DKMDT_VPPR_IDENTITY_OFFSET90|90|2|
|6|D3DKMDT_VPPR_ROTATE90_OFFSET90|180|3|
|7|D3DKMDT_VPPR_ROTATE180_OFFSET90|270|4|
|8|D3DKMDT_VPPR_ROTATE270_OFFSET90|0|1|
|9|D3DKMDT_VPPR_IDENTITY_OFFSET180|180|3|
|10|D3DKMDT_VPPR_ROTATE90_OFFSET180|270|4|
|11|D3DKMDT_VPPR_ROTATE180_OFFSET180|0|1|
|12|D3DKMDT_VPPR_ROTATE270_OFFSET180|90|2|
|13|D3DKMDT_VPPR_IDENTITY_OFFSET270|270|4|
|14|D3DKMDT_VPPR_ROTATE90_OFFSET270|0|1|
|15|D3DKMDT_VPPR_ROTATE180_OFFSET270|90|2|
|16|D3DKMDT_VPPR_ROTATE270_OFFSET270|180|3|

## -remarks



This function is declared inline in D3dkmdt.h as:

```cpp
__inline
D3DKMDT_VIDPN_PRESENT_PATH_ROTATION 
    D3DKMDT_VPPR_GET_CONTENT_ROTATION(
        D3DKMDT_VIDPN_PRESENT_PATH_ROTATION Rotation)
{
    if ((Rotation &gt;= D3DKMDT_VPPR_IDENTITY_OFFSET90) &amp;&amp;
        (Rotation &lt;= D3DKMDT_VPPR_ROTATE270_OFFSET270))
    {
        D3DKMDT_VIDPN_PRESENT_PATH_ROTATION ContentPart = 
            D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART(Rotation);
        D3DKMDT_VIDPN_PRESENT_PATH_ROTATION OffsetPart =
            D3DKMDT_VPPR_GET_OFFSET_ROTATION(Rotation);
        Rotation = (D3DKMDT_VIDPN_PRESENT_PATH_ROTATION)(
            (((ContentPart - 1) + (OffsetPart - 1)) % 4) + 1);
    }
    return Rotation;
}
```

If the content being presented has to be rotated by the driver, the output of this function represents the total rotation (the <b>Rotate</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562005">DXGK_PRESENTFLAGS</a> structure) that the driver needs to apply to the pixels provided in the <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> operation. For more info, see <a href="https://msdn.microsoft.com/136CEDA5-2839-4E6E-A032-1A9222C769C6">Supporting Path-Independent Rotation</a>.

Here's an example of how this function can provide your driver with the info it needs to properly rotate content. When a portrait-first device is connected in clone mode to a landscape-first monitor and  the user changes the <b>Orientation</b> in the <b>Display</b> control panel to <b>Portrait</b>, this represents the default orientation of the portrait-first device. Therefore the driver should set a value of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>.<b>D3DKMDT_VPPR_ROTATE90_OFFSET270</b> on the path. This function will then return a <i>Rotation</i> value of 1 (identity) to indicate that the content displayed on the clone path is not to be rotated.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn653323">D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn653324">D3DKMDT_VPPR_GET_OFFSET_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562005">DXGK_PRESENTFLAGS</a>



<a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a>
 

 

