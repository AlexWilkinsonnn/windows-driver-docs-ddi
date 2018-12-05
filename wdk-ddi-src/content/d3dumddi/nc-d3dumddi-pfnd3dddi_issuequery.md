---
UID: NC:d3dumddi.PFND3DDDI_ISSUEQUERY
title: PFND3DDDI_ISSUEQUERY
author: windows-driver-content
description: The IssueQuery function processes a query.
old-location: display\issuequery.htm
tech.root: display
ms.assetid: e31b2b6a-3721-472a-8044-6516a8419ad3
ms.date: 05/10/2018
ms.keywords: IssueQuery, IssueQuery callback function [Display Devices], PFND3DDDI_ISSUEQUERY, PFND3DDDI_ISSUEQUERY callback, UserModeDisplayDriver_Functions_59755967-2a97-4c5c-9210-c4e85cdcdd38.xml, d3dumddi/IssueQuery, display.issuequery
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	IssueQuery
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_ISSUEQUERY callback function


## -description


The <i>IssueQuery</i> function processes a query.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543192">D3DDDIARG_ISSUEQUERY</a> structure that describes how to process the query.


## -returns



<i>IssueQuery</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The query is successfully processed.|
|E_OUTOFMEMORY|IssueQuery could not allocate the required memory for it to complete.|


## -remarks



The user-mode display driver should set a fence value and store the fence value in the driver's private query structure. The user-mode display driver implements the query by using a fence. If the <i>IssueQuery</i> function is called on a query again before a previous query issue completes, the driver should overwrite the fence value and ignore the previous query issue.

If the call to <i>IssueQuery</i> requires the driver to return data, the driver should insert a graphics processing unit (GPU) instruction to write the required data to an allocation. In the call to the <a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a> function, the driver should typically lock the allocation and return the appropriate data.




## -see-also




<a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543192">D3DDDIARG_ISSUEQUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
 

 

