---
UID: NS:hbapiwmi._SM_GetBindingCapability_IN
title: _SM_GetBindingCapability_IN (hbapiwmi.h)
description: The SM_GetBindingCapability_IN structure is used to provide input parameters to the SM_GetBindingCapability method.
old-location: storage\sm_getbindingcapability_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_GetBindingCapability_IN structure"]
ms.keywords: "*PSM_GetBindingCapability_IN, PSM_GetBindingCapability_IN, PSM_GetBindingCapability_IN structure pointer [Storage Devices], SM_GetBindingCapability_IN, SM_GetBindingCapability_IN structure [Storage Devices], _SM_GetBindingCapability_IN, hbapiwmi/PSM_GetBindingCapability_IN, hbapiwmi/SM_GetBindingCapability_IN, storage.sm_getbindingcapability_in, structs-Fibre_0aed53e6-0683-4d6c-94c7-30ee531084ab.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
targetos: Windows
req.typenames: SM_GetBindingCapability_IN, *PSM_GetBindingCapability_IN
f1_keywords:
 - _SM_GetBindingCapability_IN
 - hbapiwmi/_SM_GetBindingCapability_IN
 - PSM_GetBindingCapability_IN
 - hbapiwmi/PSM_GetBindingCapability_IN
 - SM_GetBindingCapability_IN
 - hbapiwmi/SM_GetBindingCapability_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SM_GetBindingCapability_IN
 - PSM_GetBindingCapability_IN
 - SM_GetBindingCapability_IN
---

# _SM_GetBindingCapability_IN structure


## -description

The SM_GetBindingCapability_IN structure is used to provide input parameters to the SM_GetBindingCapability method.

## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.

### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.

## -remarks

The WMI tool suite generates a declaration of the SM_GetBindingCapability_IN structure in <i>Hbapiwmi.h</i> when it compiles the SM_TargetInformationMethod WMI class.

