---
UID: NC:sercx.EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START
title: EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START (sercx.h)
description: The EvtSerCx2CustomTransmitTransactionStart event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-transmit transaction.
old-location: serports\evtsercx2customtransmittransactionstart.htm
tech.root: serports
ms.assetid: BFB2DBBE-9E00-4C1D-B336-2B9C48E98DD3
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2CustomTransmitTransactionStart, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START callback, EvtSerCx2CustomTransmitTransactionStart, EvtSerCx2CustomTransmitTransactionStart callback function [Serial Ports], serports.evtsercx2customtransmittransactionstart
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	2.0\Sercx.h
api_name:
-	EvtSerCx2CustomTransmitTransactionStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START callback function


## -description


The <i>EvtSerCx2CustomTransmitTransactionStart</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-transmit transaction.


## -parameters




### -param CustomTransmitTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit-transaction object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a> method to create this object.


### -param Request [in]

A handle to the framework request object associated with the custom-transmit transaction. The driver is responsible for completing this request. This request might not be the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request sent by the client, and thus the serial controller driver should not try to use this request to access the write buffer. This request is primarily used for cancellation, completion, and queue forwarding (if needed). To access the write buffer for the client's write request, use the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.


### -param Mdl [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> that describes the memory pages that are spanned by the write buffer for the custom-transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns



None.




## -remarks



Your serial controller driver must implement this function if it creates a custom-transmit-transaction object. If implemented, the driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a> call that creates this object.

After SerCx2 calls the <i>EvtSerCx2CustomTransmitTransactionStart</i> function, the serial controller driver initiates the transaction by programming the custom data-transfer mechanism to move data from the buffer in the write request to the transmit FIFO in the serial controller hardware. Unless the request can be completed immediately, before the <i>EvtSerCx2CustomTransmitTransactionStart</i> function returns, the driver must call a method such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to mark the request as cancelable.

After the transaction finishes and the driver completes the pending write request, SerCx2 calls the <a href="https://msdn.microsoft.com/CEADF06B-FD60-4B4C-AB59-1ED6B1226204">EvtSerCx2CustomTransmitTransactionCleanup</a> event callback function, if the driver implements this function.

If the serial controller driver implements an <a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a> event callback function, SerCx2 calls this function before calling the <i>EvtSerCx2CustomTransmitTransactionStart</i> function. Just before the <i>EvtSerCx2CustomTransmitTransactionStart</i> call, and after the <i>EvtSerCx2CustomTransmitTransactionInitialize</i> call returns, SerCx2 starts the timer that detects whether the write request times out. For more information, see the discussion of total time-outs in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>.

The serial controller driver should complete the pending write request only after the last byte in the transmit FIFO has been transmitted to the serially connected peripheral device. There can be no guarantee that data written to the transmit FIFO will be transmitted without a significant delay, and a serial controller driver that assumes that such a guarantee exists can cause reliability problems for peripheral drivers.

If the custom data-transfer mechanism is a bus-master DMA device, the <i>EvtSerCx2CustomTransmitTransactionStart</i> function can call a method such as <a href="https://msdn.microsoft.com/library/windows/hardware/hh451182">WdfDmaTransactionInitializeUsingOffset</a> to initiate a DMA transaction that uses the write buffer described by the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

For more information about the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters, see Remarks in <a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a>.

If the request object identified by the <i>Request</i> parameter contains storage for a private context, this storage might be uninitialized the first time the serial controller driver accesses the context. On first access, the driver typically should fill the context with zeros, and then, if needed, explicitly set any fields in the context that require nonzero initial values.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2CustomTransmitTransactionStart</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2CustomTransmitTransactionStart</i> callback function that is named <code>MyCustomTransmitTransactionStart</code>, use the <b>EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START  MyCustomTransmitTransactionStart;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyCustomTransmitTransactionStart(
    SERCX2CUSTOMTRANSMITTRANSACTION  CustomTransmitTransaction,
    WDFREQUEST  Request,
    PMDL  Mdl,
    ULONG  Offset,
    ULONG  Length
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/CEADF06B-FD60-4B4C-AB59-1ED6B1226204">EvtSerCx2CustomTransmitTransactionCleanup</a>



<a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451182">WdfDmaTransactionInitializeUsingOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>
 

 

