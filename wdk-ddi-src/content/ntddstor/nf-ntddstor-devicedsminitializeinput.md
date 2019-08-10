---
UID: NF:ntddstor.DeviceDsmInitializeInput
title: DeviceDsmInitializeInput function (ntddstor.h)
description: The DeviceDsmInitializeInput function initializes a DEVICE_DSM_INPUT structure.
ms.assetid: 4a212a8e-1bd1-4ad1-9da1-f9527a304e81
tech.root: storage
ms.date: 08/15/2019
ms.topic: function
f1_keywords:
 - "ntddstor/DeviceDsmInitializeInput"
ms.keywords: DeviceDsmInitializeInput
req.header: ntddstor.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- DeviceDsmInitializeInput
product:
- Windows
targetos: Windows

---

# DeviceDsmInitializeInput function

## -description

The **DeviceDsmInitializeInput** function initializes the [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) structure and parameters block of an input operation.

## -parameters

### -param Definition

Pointer to an opaque [DEVICE_DSM_DEFINITION](ns-ntddstor-_device_dsm_definition.md) structure that contains parameter block alignment and length information.

### -param Input

Pointer to the caller-allocated [DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md) input structure.

### -param InputLength

The length, in bytes, to write to the input.

### -param Flags

Flags for global control actions for the input.

### -param Parameters

Parameters for initializing the parameter block of the input structure. See Remarks.

### -param ParameterBlockLength

The length, in bytes, of the parameter block.

## -returns

This function does not return a value.

## -remarks

The parameter block is formatted as a [DEVICE_DSM_NOTIFICATION_PARAMETERS](ns-ntddstor-_device_dsm_notification_parameters.md) structure.

To add a data set range to the input operation, call [**DeviceDsmAddDataSetRange**](nf-ntddstor-devicedsmadddatasetrange).

## -see-also

[DEVICE_DSM_INPUT](ns-ntddstor-_device_manage_data_set_attributes.md)

[**DeviceDsmAddDataSetRange**](nf-ntddstor-devicedsmadddatasetrange)
