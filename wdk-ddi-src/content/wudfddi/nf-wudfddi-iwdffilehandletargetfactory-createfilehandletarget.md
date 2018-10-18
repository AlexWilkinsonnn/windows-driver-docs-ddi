---
UID: NF:wudfddi.IWDFFileHandleTargetFactory.CreateFileHandleTarget
title: IWDFFileHandleTargetFactory::CreateFileHandleTarget
author: windows-driver-content
description: The CreateFileHandleTarget method creates a file-handle-based I/O target object.
old-location: wdf\iwdffilehandletargetfactory_createfilehandletarget.htm
tech.root: wdf
ms.assetid: 579a2cef-1e37-426c-9f69-8766dc9011ba
ms.date: 2/26/2018
ms.keywords: CreateFileHandleTarget, CreateFileHandleTarget method, CreateFileHandleTarget method,IWDFFileHandleTargetFactory interface, IWDFFileHandleTargetFactory interface,CreateFileHandleTarget method, IWDFFileHandleTargetFactory.CreateFileHandleTarget, IWDFFileHandleTargetFactory::CreateFileHandleTarget, UMDFDeviceObjectRef_4a3fcfeb-e1a1-4375-8bd5-bdd75c36c454.xml, umdf.iwdffilehandletargetfactory_createfilehandletarget, wdf.iwdffilehandletargetfactory_createfilehandletarget, wudfddi/IWDFFileHandleTargetFactory::CreateFileHandleTarget
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfusb.h
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
-	IWDFFileHandleTargetFactory.CreateFileHandleTarget
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFFileHandleTargetFactory::CreateFileHandleTarget


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateFileHandleTarget</b> method creates a file-handle-based I/O target object.


## -parameters




### -param hTarget [in]

A handle to the target device. The handle must have been previously opened with the FILE_FLAG_OVERLAPPED flag. For example, FILE_FLAG_OVERLAPPED must have been specified in the <i>dwFlagsAndAttributes</i> parameter of the Microsoft Win32 <b>CreateFile</b> function. 


### -param ppTarget [out]

A pointer to a location that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a> interface of the I/O target object.


## -returns



<b>CreateFileHandleTarget</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/579a2cef-1e37-426c-9f69-8766dc9011ba">CreateFileHandleTarget</a> successfully created a file-handle-based I/O target object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/579a2cef-1e37-426c-9f69-8766dc9011ba">CreateFileHandleTarget</a> encountered an allocation failure.

</td>
</tr>
</table>
 

<b>CreateFileHandleTarget</b> might also return other HRESULT values that are defined in Winerror.h.






## -remarks



If your driver uses a file-handle-based I/O target, the <b>DDInstall.WDF</b> section of the driver's INF file must set the <b>UmdfDispatcher</b> directive to <b>FileHandle</b>. For more information about <b>UmdfDispatcher</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives</a>.

After the driver creates a file-handle-based I/O target object, it can format I/O requests and send them to the I/O target. Typically, if the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559230">IWDFIoTarget::FormatRequestForIoctl</a>, the driver sets the <i>pFile</i> parameter to <b>NULL</b>. The <b>NULL</b> causes the framework to use the filename that the driver specified to <b>CreateFileHandleTarget</b>. If the driver provides a non-<b>NULL</b> <i>pFile</i> parameter, the specified file replaces the file that the driver specified to <b>CreateFileHandleTarget</b>. (Drivers can also call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559077">IWDFIoRequest::FormatUsingCurrentType</a> to format an I/O request.)

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> to send the I/O request to the I/O target, the driver must not set the <a href="https://msdn.microsoft.com/02678466-aa8d-436d-8be3-b8a57218a106">WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</a> value in the <i>Flags</i> parameter. 

The Win32 handle that the driver passes to <b>CreateFileHandleTarget</b> must remain valid for the lifetime of the file-handle-based I/O target object. (The framework does not take a reference on this target handle, so your driver must ensure that the Win32 handle remains valid.)

When the driver has finished using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a> interface that <b>CreateFileHandleTarget</b> provides, it must release the <b>IWDFIoTarget</b> interface.

For more information about <b>CreateFileHandleTarget</b> and I/O targets, see <a href="https://msdn.microsoft.com/cf1b39c3-4c82-411b-8eef-117ac0fe793e">Initializing a General I/O Target in UMDF</a>.


#### Examples

The following code example shows how to create a file-handle-based I/O target for a named pipe. In this example, <i>m_FxDevice</i> is the interface pointer that <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> provides.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT hr = S_OK;
CComPtr&lt;IWDFFileHandleTargetFactory&gt; pFileHandleTargetFactory;
//
// Create a pipe and get the handle.
//
m_WriteHandle = CreateNamedPipe(NP_NAME, 
                                PIPE_ACCESS_DUPLEX|FILE_FLAG_OVERLAPPED, 
                                PIPE_TYPE_MESSAGE|PIPE_READMODE_MESSAGE|PIPE_WAIT,
                                2,
                                MAX_TRANSFER_SIZE,
                                MAX_TRANSFER_SIZE,
                                1000,
                                NULL);
if (m_WriteHandle == INVALID_HANDLE_VALUE) {
    DWORD err = GetLastError();
    hr = HRESULT_FROM_WIN32(err);
}
//
// Obtain the IWDFFileHandleTargetFactory interface
// by calling IWDFDevice::QueryInterface. 
//
if (SUCCEEDED(hr)) {
    hr = m_FxDevice-&gt;QueryInterface(IID_PPV_ARGS(&amp;pFileHandleTargetFactory));
}
//
// Create a file handle target.
//
if (SUCCEEDED(hr)) {
    hr = pFileHandleTargetFactory-&gt;CreateFileHandleTarget(m_WriteHandle,
                                                          &amp;m_WriteTarget);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558926">IWDFFileHandleTargetFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>
 

 

