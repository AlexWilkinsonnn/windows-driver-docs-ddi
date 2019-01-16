---
UID: NN:wudfddi.IWDFObject
title: IWDFObject
description: The IWDFObject interface exposes the framework base object that provides the basic functionality common across all framework object types. All framework objects are derived from this root object.
old-location: wdf\iwdfobject.htm
tech.root: wdf
ms.assetid: d2668856-a25d-4329-b230-f36992f8f9a4
ms.date: 02/26/2018
ms.keywords: IWDFObject, IWDFObject interface, IWDFObject interface,described, UMDFBaseObjectRef_b2026a30-0f91-4793-8622-093ca142f794.xml, umdf.iwdfobject, wdf.iwdfobject, wudfddi/IWDFObject
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFObject interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFObject</b> interface exposes the framework base object that provides the basic functionality common across all framework object types. All framework objects are derived from this root object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFObject</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IWDFObject</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFObject</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560204">IWDFObject::AcquireLock</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/f69328fb-356b-4381-ae6e-df39ac60e032">AcquireLock</a> method prevents the framework from calling methods of interfaces that a driver registered.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/9b543d5d-ed6d-4440-b5ad-aefca69dd489">AssignContext</a> method registers a context and a driver-supplied cleanup callback function for the object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/a777b8df-e255-402a-aa55-14e5861b215f">DeleteWdfObject</a> method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560214">IWDFObject::ReleaseLock</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/05771d81-d2e1-4787-a190-e7ef4d9ebcc9">ReleaseLock</a> method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560204">IWDFObject::AcquireLock</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560218">IWDFObject::RetrieveContext</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/b76acae1-3c37-4095-bf8b-1785dc90f378">RetrieveContext</a> method retrieves a context that was previously registered through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a> method.

</td>
</tr>
</table> 

