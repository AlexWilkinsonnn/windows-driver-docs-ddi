---
UID: NF:wdfinstaller.WdfPreDeviceRemove
title: WdfPreDeviceRemove function
author: windows-driver-content
description: The co-installer's WdfPreDeviceRemove function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer deletes the driver's kernel-mode service.
old-location: wdf\wdfpredeviceremove.htm
tech.root: wdf
ms.assetid: 8cde623d-a255-45ff-ab1e-bdd0c14a02a0
ms.date: 02/26/2018
ms.keywords: DFCoinstallerRef_6eeb3b62-08ef-4d17-a6af-9945a3737f0d.xml, WdfPreDeviceRemove, WdfPreDeviceRemove function, kmdf.wdfpredeviceremove, wdf.wdfpredeviceremove, wdfinstaller/WdfPreDeviceRemove
ms.topic: function
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	N/A
-	N/A.dll
api_name:
-	WdfPreDeviceRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPreDeviceRemove function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The co-installer's <b>WdfPreDeviceRemove</b> function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer deletes the driver's kernel-mode service. 


## -parameters




### -param InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <a href="https://msdn.microsoft.com/1fbe6289-2ca8-4ca8-b004-ecf513f9b0bd">GetCurrentDirectory</a>, which is described in the Microsoft Windows SDK.


### -param InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


## -returns



<b>WdfPreDeviceRemove</b> returns <b>ERROR_SUCCESS</b> if the operation succeeds. Otherwise, the function returns one of the additional <b>ERROR_XXX</b> values that are defined in Winerror.h.




## -remarks



The installer for the framework-based drivers of a non-PnP device must call <b>WdfPreDeviceRemove</b> before the installer calls <a href="https://msdn.microsoft.com/5b0fc714-60e0-4ae3-8fa8-ace36dab2fb0">DeleteService</a>.

To obtain the address of the co-installer's <b>WdfPreDeviceRemove</b> function, the installer must call <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a> after the installer has called <a href="https://msdn.microsoft.com/d936b4dd-058c-48e1-834b-b47ef6d8ef65">LoadLibrary</a> to load the co-installer.

For more information about the <b>WdfPreDeviceRemove</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <a href="https://msdn.microsoft.com/5b0fc714-60e0-4ae3-8fa8-ace36dab2fb0">DeleteService</a>, <a href="https://msdn.microsoft.com/a0d7fc09-f888-4f46-a571-d3719a627597">GetProcAddress</a>, and <a href="https://msdn.microsoft.com/d936b4dd-058c-48e1-834b-b47ef6d8ef65">LoadLibrary</a>, see the Microsoft Windows SDK documentation.


#### Examples

For a code example that uses the <b>WdfPreDeviceRemove</b> function, see the installer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548833">WdfPostDeviceRemove</a>
 

 

