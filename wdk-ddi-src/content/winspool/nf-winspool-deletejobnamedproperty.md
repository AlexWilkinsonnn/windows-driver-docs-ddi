---
UID: NF:winspool.DeleteJobNamedProperty
title: DeleteJobNamedProperty function (winspool.h)
description: Deletes the named property for the specified print job on the specified printer.
old-location: print\deletejobnamedproperty.htm
tech.root: print
ms.assetid: 14F8C0A2-0D19-446E-8C2B-530A3AEDA879
ms.date: 04/20/2018
ms.keywords: DeleteJobNamedProperty, DeleteJobNamedProperty function [Print Devices], print.deletejobnamedproperty, winspool/DeleteJobNamedProperty
ms.topic: function
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Desktop
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
req.lib: WinSpool.lib
req.dll: Spoolss.dll; WinSpool.drv
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- spoolss.dll
- WinSpool.drv
api_name:
- DeleteJobNamedProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# DeleteJobNamedProperty function


## -description


Deletes the named property for the specified print job on the specified printer.  



## -parameters




### -param hPrinter [in]

A handle to the printer object of interest. Use the <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>, <a href="https://msdn.microsoft.com/e2370ae4-4475-4ccc-a6f9-3d33d1370054">OpenPrinter2</a>, or the <a href="https://msdn.microsoft.com/ffc4fee8-46c6-47ad-803d-623bf8efdefd">AddPrinter</a> function to retrieve a printer handle. 



### -param JobId [in]

Identifier that specifies the print job. You obtain a print job identifier by calling the <a href="https://msdn.microsoft.com/cfafa874-6022-4bf4-bf3d-096213eb0c98">AddJob</a> function or the <a href="https://msdn.microsoft.com/67580632-ff9a-4d29-8e4e-c21f04aa4b47">StartDoc</a> function. 



### -param pszName [in]

Name of the property that will be deleted. 



## -returns



If the operation succeeds, the function returns <b>ERROR_SUCCESS.</b>



