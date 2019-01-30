---
UID: NF:wdm.IoOpenDriverRegistryKey
title: IoOpenDriverRegistryKey function (wdm.h)
description: Reserved.
ms.assetid: 5166cf0f-81c2-4567-91a8-67ae6727fbdd
ms.date: 10/19/2018
ms.topic: function
ms.keywords: IoOpenDriverRegistryKey
req.header: wdm.h
req.include-header: wdm.h, ntddk.h, or ntifs.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoOpenDriverRegistryKey
product:
-	Windows
targetos: Windows

---

# IoOpenDriverRegistryKey function


## -description

The **IoOpenDriverRegistryKey** routine returns a handle to a driver specific registry key for a particular driver.

## -parameters

### -param DriverObject [in]
A pointer to a [**DRIVER_OBJECT**](ns-wdm-_driver_object.md) structure. This structure must be the driver object for the calling driver.

### -param RegKeyType [in]
A [**DRIVER_REGKEY_TYPE**](ne-wdm-driver_regkey_type.md) type value that indicates the type of the requested registry key.

### -param DesiredAccess [in]
Specifies the [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask) value that represents the access the caller needs to the key. See the [**ZwCreateKey**](nf-wdm-zwcreatekey.md) routine for a description of each KEY_XXX access right.

### -param Flags [in]
Must be 0.

### -param DriverRegKey [out]
A pointer to the HANDLE variable that, on successful return, contains a handle to the requested registry key.

## -returns
**IoOpenDriverRegistryKey** returns STATUS_SUCCESS if the call successfully opened a handle to the requested registry key.

## -remarks

The driver must call [**ZwClose**](nf-wdm-zwclose.md) to close the handle returned from this routine when access is no longer required.

The registry keys opened by this routine are nonvolatile.

To provision keys and values under the immutable **DriverRegKeyParameters** registry key, use an [AddReg directive](https://docs.microsoft.com/windows-hardware/drivers/install/inf-addreg-directive) from a service-install-section to reference an add-registry-section section that contains entries with a reg-root of `HKR` and a subkey of `Parameters`.

Callers of **IoOpenDriverRegistryKey** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.


## -see-also

[**ZwClose**](nf-wdm-zwclose.md)	

[ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[**DRIVER_REGKEY_TYPE**](ne-wdm-driver_regkey_type.md)
