---
UID: NF:portcls.IResourceList.NumberOfEntriesOfType
title: IResourceList::NumberOfEntriesOfType
author: windows-driver-content
description: The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.
old-location: audio\iresourcelist_numberofentriesoftype.htm
tech.root: audio
ms.assetid: 61645c17-9278-49e0-a0bf-24a8c52e964d
ms.date: 5/8/2018
ms.keywords: IResourceList interface [Audio Devices],NumberOfEntriesOfType method, IResourceList.NumberOfEntriesOfType, IResourceList::NumberOfEntriesOfType, NumberOfEntriesOfType, NumberOfEntriesOfType method [Audio Devices], NumberOfEntriesOfType method [Audio Devices],IResourceList interface, audio.iresourcelist_numberofentriesoftype, audmp-routines_eb0c6999-a901-4087-b7bc-12057f91be90.xml, portcls/IResourceList::NumberOfEntriesOfType
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IResourceList.NumberOfEntriesOfType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IResourceList::NumberOfEntriesOfType


## -description


The <code>NumberOfEntriesOfType</code> method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.


## -parameters




### -param Type [in]

Identifies the resource type of the entries that are to be counted. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


## -returns



<code>NumberOfEntriesOfType</code> returns the number of items of the indicated type in the resource list.




## -remarks



For each resource type, a macro is defined to call this method. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>.




## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>
 

 

