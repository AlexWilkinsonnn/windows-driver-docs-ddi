---
UID: NF:portcls.IResourceList.FindUntranslatedEntry
title: IResourceList::FindUntranslatedEntry
author: windows-driver-content
description: The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found.
old-location: audio\iresourcelist_finduntranslatedentry.htm
tech.root: audio
ms.assetid: 3578eb3a-e9c8-4de3-b959-daff9ac7f1a2
ms.date: 05/08/2018
ms.keywords: FindUntranslatedEntry, FindUntranslatedEntry method [Audio Devices], FindUntranslatedEntry method [Audio Devices],IResourceList interface, IResourceList interface [Audio Devices],FindUntranslatedEntry method, IResourceList.FindUntranslatedEntry, IResourceList::FindUntranslatedEntry, audio.iresourcelist_finduntranslatedentry, audmp-routines_d9b98845-63dd-454d-b1de-dd7db8825e27.xml, portcls/IResourceList::FindUntranslatedEntry
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
-	IResourceList.FindUntranslatedEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# IResourceList::FindUntranslatedEntry


## -description


The <code>FindUntranslatedEntry</code> method returns a pointer to an untranslated entry of the specified type, or <b>NULL</b> if no such pointer is found.


## -parameters




### -param Type [in]

Identifies the resource type of the entries that are to be counted. For a list of valid values, see the <b>Type</b> member of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


### -param Index [in]

Specifies the index of the entry to find. If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the untranslated version of the first occurrence of an entry of the specified type from the resource list.


## -returns



<code>FindUntranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource object is deleted.




## -remarks



For each resource type, a macro is defined to call this method. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>.

The <i>Index</i> parameter indicates which occurrence of an entry of the specified type to find in the list of translated resource entries. The first occurrence in the list has an index of zero.

For each resource type, a macro is defined to call this method. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>.

For more information about translated and untranslated (or "raw") resources, see <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.




## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536982">IResourceList::FindTranslatedEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a>
 

 

