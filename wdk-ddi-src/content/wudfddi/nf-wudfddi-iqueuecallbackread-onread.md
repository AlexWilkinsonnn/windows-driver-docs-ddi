---
UID: NF:wudfddi.IQueueCallbackRead.OnRead
title: IQueueCallbackRead::OnRead
author: windows-driver-content
description: The OnRead method is called to handle a read request when an application reads information from a device through the Microsoft Win32 ReadFile or ReadFileEx function.
old-location: wdf\iqueuecallbackread_onread.htm
tech.root: wdf
ms.assetid: e11a823d-0b08-42fd-b093-4c464c152afe
ms.date: 02/26/2018
ms.keywords: IQueueCallbackRead interface,OnRead method, IQueueCallbackRead.OnRead, IQueueCallbackRead::OnRead, OnRead, OnRead method, OnRead method,IQueueCallbackRead interface, UMDFQueueObjectRef_56f5bb6c-4b65-4ab9-961a-278bfc6dbfe9.xml, umdf.iqueuecallbackread_onread, wdf.iqueuecallbackread_onread, wudfddi/IQueueCallbackRead::OnRead
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IQueueCallbackRead.OnRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackRead::OnRead


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnRead</b> method is called to handle a read request when an application reads information from a device through the Microsoft Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function. 


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from. 


### -param pWdfRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object. 


### -param NumOfBytesToRead [in]

The size, in bytes, of the read buffer for the request.


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556872">IQueueCallbackRead</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

A driver can implement a single <b>OnRead</b> method for all I/O queues or separate <b>OnRead</b> methods for each I/O queue. 

The <b>OnRead</b> method receives every read request type from the queue. (The read request type is identified by the <b>WdfRequestRead</b> value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a> enumeration type for the request.) The <b>OnRead</b> method must process each received read request. For more information about how UMDF drivers process I/O requests, see <a href="https://msdn.microsoft.com/90b1cc51-da40-45c1-9d6c-57f637f474d9">Processing I/O Requests</a>.

The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559113">IWDFIoRequest::GetReadParameters</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a> methods to retrieve information about the request and the read buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556872">IQueueCallbackRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>
 

 

