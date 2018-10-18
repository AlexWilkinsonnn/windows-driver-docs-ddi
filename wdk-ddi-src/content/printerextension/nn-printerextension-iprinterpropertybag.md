---
UID: NN:printerextension.IPrinterPropertyBag
title: IPrinterPropertyBag
author: windows-driver-content
description: Provides strongly-typed get and set methods.
old-location: print\iprinterpropertybag_interface.htm
tech.root: print
ms.assetid: 421397FF-4956-4052-B63D-32F8E79A22D0
ms.date: 4/20/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], IPrinterPropertyBag interface [Print Devices],described, print.iprinterpropertybag_interface, printerextension/IPrinterPropertyBag
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterPropertyBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterPropertyBag interface


## -description


Provides strongly-typed <b>get</b> and <b>set</b> methods.

Note that the driver property bag uses the following GUID for its property store format ID:

<dl>
<dd>DEFINE_GUID(FMTID_PrinterPropertyBag, 0x75f9adca, 0x097d, 0x45c3, 0xa6, 0xe4, 0xba, 0xb2, 0x9e, 0x27, 0x6f, 0x3e);</dd>
</dl>


The <b>IPrinterPropertyBag</b> interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterPropertyBag</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterPropertyBag</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterPropertyBag</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439647">GetBool</a>
</td>
<td align="left" width="63%">
Reads a specified boolean property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439653">GetBytes</a>
</td>
<td align="left" width="63%">
Reads a byte array property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439658">GetInt32</a>
</td>
<td align="left" width="63%">
Reads an integer property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439535">GetReadStream</a>
</td>
<td align="left" width="63%">
Gets a stream in order to read from a stream property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>
</td>
<td align="left" width="63%">
Reads a string property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439675">GetWriteStream</a>
</td>
<td align="left" width="63%">
Gets a stream in order to write a stream property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439552">SetBool</a>
</td>
<td align="left" width="63%">
Writes a specified boolean property value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439606">SetBytes</a>
</td>
<td align="left" width="63%">
Writes a byte array property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439610">SetInt32</a>
</td>
<td align="left" width="63%">
Writes an integer property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a>
</td>
<td align="left" width="63%">
Writes a string property.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a>



<a href="https://msdn.microsoft.com/52EC01D5-43C7-4CE0-ABEC-1604A4198316">IPrinterExtensionContext::DriverProperties</a>



<a href="https://msdn.microsoft.com/21B370C9-BDF7-42A6-B0CC-BC9B19F9D2D5">IPrinterExtensionContext::UserProperties</a>



<a href="https://msdn.microsoft.com/87EED8B5-676C-4056-812B-B0424148FCFA">IPrinterQueue::GetProperties</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>



<a href="https://msdn.microsoft.com/4E20303A-BEB3-4928-BA5A-356D978FA2BE">V4 Printer Driver Property Bags</a>
 

 

