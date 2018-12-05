---
UID: NC:ndis.PROTOCOL_STATUS_EX
title: PROTOCOL_STATUS_EX
author: windows-driver-content
description: The ProtocolStatusEx function indicates status-changes from underlying connectionless drivers or NDIS.Note  You must declare the function by using the PROTOCOL_STATUS_EX type.
old-location: netvista\protocolstatusex.htm
tech.root: netvista
ms.assetid: 5bc5a24f-5f28-4502-8776-b1cf15fd8283
ms.date: 05/02/2018
ms.keywords: PROTOCOL_STATUS_EX, PROTOCOL_STATUS_EX callback, ProtocolStatusEx, ProtocolStatusEx callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolStatusEx, ndis_status_ref_c14c8c6e-b2ed-41a7-a4da-c7415ee8b290.xml, netvista.protocolstatusex
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolStatusEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_STATUS_EX callback function


## -description


The 
  <i>ProtocolStatusEx</i> function indicates status-changes from underlying connectionless drivers or
  NDIS.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_STATUS_EX</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area that the protocol driver allocated. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


### -param StatusIndication [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## -returns



None




## -remarks



A call to 
    <i>ProtocolStatusEx</i> notifies the protocol driver about changes in status of an underlying driver.

To determine link status, use the status indications from underlying drivers instead of OID queries.
    These status indications will improve system performance and avoid possible race conditions.

NDIS calls the 
    <i>ProtocolStatusEx</i> function of all bound protocol drivers when an underlying driver is resetting a
    NIC. First NDIS specifies the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567420">NDIS_STATUS_RESET_START</a> code and
    later, when the reset operation is complete, NDIS specifies the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567419">NDIS_STATUS_RESET_END</a> code.

NDIS will not accept send requests and OID requests for a miniport adapter while a reset operation is
    in progress, the NDIS_STATUS_RESET_START notification warns bound protocol drivers to stop such requests
    on the affected binding until they receive the corresponding NDIS_STATUS_RESET_END notification.

NDIS calls 
    <i>ProtocolStatusEx</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolStatusEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolStatusEx</i> function that is named "MyStatusEx", use the <b>PROTOCOL_STATUS_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_STATUS_EX MyStatusEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyStatusEx(
    NDIS_HANDLE  ProtocolBindingContext,
    PNDIS_STATUS_INDICATION  StatusIndication
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_STATUS_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_STATUS_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567419">NDIS_STATUS_RESET_END</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567420">NDIS_STATUS_RESET_START</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
 

 

