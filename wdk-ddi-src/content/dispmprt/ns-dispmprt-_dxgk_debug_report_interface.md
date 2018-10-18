---
UID: NS:dispmprt._DXGK_DEBUG_REPORT_INTERFACE
title: "_DXGK_DEBUG_REPORT_INTERFACE"
author: windows-driver-content
description: The DXGK_DEBUG_REPORT_INTERFACE structure contains pointers to functions in the Debug Report interface, which is implemented by the display port driver.
old-location: display\dxgk_debug_report_interface.htm
tech.root: display
ms.assetid: fb1bd1dd-feab-4aa4-8b4f-932f0d5ec4ab
ms.date: 5/10/2018
ms.keywords: "*PDXGK_DEBUG_REPORT_INTERFACE, DXGK_DEBUG_REPORT_INTERFACE, DXGK_DEBUG_REPORT_INTERFACE structure [Display Devices], DmStructs_b6b70526-c889-47d8-bfb7-7f961cbcef38.xml, PDXGK_DEBUG_REPORT_INTERFACE, PDXGK_DEBUG_REPORT_INTERFACE structure pointer [Display Devices], _DXGK_DEBUG_REPORT_INTERFACE, display.dxgk_debug_report_interface, dispmprt/DXGK_DEBUG_REPORT_INTERFACE, dispmprt/PDXGK_DEBUG_REPORT_INTERFACE"
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_DEBUG_REPORT_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: DXGK_DEBUG_REPORT_INTERFACE, *PDXGK_DEBUG_REPORT_INTERFACE
---

# _DXGK_DEBUG_REPORT_INTERFACE structure


## -description


The DXGK_DEBUG_REPORT_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551798">Debug Report interface</a>, which is implemented by the display port driver.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the Debug Report interface. Version number constants are defined in <i>Dispmprt.h</i> (for example, DXGK_DEBUG_REPORT_INTERFACE_VERSION_1).


### -field Context

A pointer to a context that is provided by the display port driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display port driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display port driver.


### -field DbgReportCreate

Creates an initial error report.

This function is available in Windows Vista and later operating systems.

If your display miniport driver detects a failure and then recovers from it, you can create an error report that can later be used for debugging. First, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a>to create an initial report. Then add data to the report by making one or more calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549099">DbgReportSecondaryData</a>. When you have finished adding data to the report, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549080">DbgReportComplete</a>.



#### DeviceHandle

A handle to a context block associated with a display adapter. The display miniport driver created this handle in its <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function. This parameter can be <b>NULL</b>.



#### ulCode

A code for the error report. The following codes are supported:

<ul>
<li>
THREAD_STUCK_IN_DEVICE_DRIVER

</li>
<li>
VIDEO_DRIVER_DEBUG_REPORT_REQUEST

</li>
<li>
VIDEO_TDR_FATAL_ERROR

</li>
<li>
VIDEO_TDR_SUCCESS

</li>
</ul>


#### ulpArg1

The first argument to be added to the report. The developer of the display miniport driver determines the value and meaning of <i>ulpArg1</i>.



#### ulpArg2

The second argument to be added to the report. The developer of the display miniport driver determines the value and meaning of <i>ulpArg2</i>.



#### ulpArg3

The third argument to be added to the report. The developer of the display miniport driver determines the value and meaning of <i>ulpArg3</i>.



#### ulpArg4

Reserved.


### -field DbgReportSecondaryData

appends data to an initial error report that was previously created by DbgReportCreate.

This function is available in Windows Vista and later operating systems.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549099">DbgReportSecondaryData</a> to add data to an initial report that was created by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a>. You can call <b>DbgReportSecondaryData</b> several times, but with each call, the data written to the report overwrites the data written by the previous call. The following steps give a good strategy for incrementally adding data to the report.

<ol>
<li>
Obtain the data that is safest to collect. 

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549099">DbgReportSecondaryData</a> to write that data to the report. 

</li>
<li>
Obtain data that is more risky to collect. 

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549099">DbgReportSecondaryData</a> to write the original safe data along with the newly collected risky data to the report. You must include both the safe and the risky data in this call because the data written by this call overwrites the data written by the first call to <b>DbgReportSecondaryData</b>. 

</li>
<li>
Continue calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549099">DbgReportSecondaryData</a>, enhancing the data each time, until you have no more data to add. 

</li>
<li>
When you have finished adding data to the report, close the report by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549080">DbgReportComplete</a>. The report is stored in a file and sent to Microsoft when the computer is rebooted.

</li>
<li>
If the computer stops responding before you call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549080">DbgReportComplete</a>, the data added to the report by the most recent successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549099">DbgReportSecondaryData</a> is saved and then sent to Microsoft when the computer is rebooted.

</li>
</ol>


#### hReport

A handle to the error report to which data will be appended. The display miniport driver previously obtained this handle by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a>.



#### pvData

A pointer to a buffer that holds the data to be added to the report.



#### ulDataSize

The size, in bytes, of the data to be added to the report. The value of this parameter must be less than or equal to DXGK_DEBUG_REPORT_MAX_SIZE.


### -field DbgReportComplete

Closes an error report and frees any resources associated with the report.

This function is available in Windows Vista and later operating systems. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a> creates an entry in the system event log and displays a dialog box that informs the user of the failure and presents the opportunity to upload an error report to Microsoft.

The error report is saved in a file and scheduled to be sent to Microsoft when the computer is rebooted. The error report contains an error code and four arguments. The error code and the first three arguments are provided by the caller of <a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a>. The fourth argument in the report is provided by the operating system and indicates the number of reports generated since the computer was started. For example, if the value of the fourth argument is 5, this means that four previous error reports were generated by the display miniport driver since the computer was last started. Only the fifth report is saved because each report overwrites the previous one.



#### hReport

A handle to the error report that is to be closed. The display miniport driver previously obtained this handle by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a>.


## -remarks



The display miniport driver supplies the <b>Size</b> and <b>Version</b> members of this structure, and then calls <a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a>, which fills in the remaining members of this structure.



