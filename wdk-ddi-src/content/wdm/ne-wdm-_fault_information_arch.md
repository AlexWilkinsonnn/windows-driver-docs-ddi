---
UID: NE:wdm._FAULT_INFORMATION_ARCH
title: _FAULT_INFORMATION_ARCH (wdm.h)
description: Defines values for type of system architecture.
ms.assetid: cee58e78-b1d7-471f-80e4-c1aa4e5189a5
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: _FAULT_INFORMATION_ARCH, *PFAULT_INFORMATION_ARCH, FAULT_INFORMATION_ARCH, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: FAULT_INFORMATION_ARCH, *PFAULT_INFORMATION_ARCH
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	_FAULT_INFORMATION_ARCH
product:
-	Windows
targetos: Windows
---

# _FAULT_INFORMATION_ARCH enumeration

## -description

Defines values for type of system architecture specified in the [_IOMMU_DOMAIN_FAULT_HANDLER_](nc-wdm-iommu_domain_fault_handler.md) callback function.


## -enum-fields

### -field FaultInformationInvalid 
The architecture type is not valid. 

### -field FaultInformationArm64
ARM64 architecture.

## -remarks

## -see-also
[_IOMMU_DOMAIN_FAULT_HANDLER_](nc-wdm-iommu_domain_fault_handler.md)
