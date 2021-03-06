---
UID: NF:winppi.GdiResetDCEMF
title: GdiResetDCEMF function (winppi.h)
description: The GdiResetDCEMF function resets a printer's device context during playback of a spooled EMF print job.
old-location: print\gdiresetdcemf.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["GdiResetDCEMF function"]
ms.keywords: GdiResetDCEMF, GdiResetDCEMF function [Print Devices], gdifnc_ff066b35-7062-430e-a8b9-bbdef46494a6.xml, print.gdiresetdcemf, winppi/GdiResetDCEMF
req.header: winppi.h
req.include-header: Winppi.h
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
req.lib: Gdi32.Lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - GdiResetDCEMF
 - winppi/GdiResetDCEMF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
 - GDI32Full.dll
api_name:
 - GdiResetDCEMF
---

# GdiResetDCEMF function


## -description

The <b>GdiResetDCEMF</b> function resets a printer's device context during playback of a spooled EMF print job.

## -parameters

### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>.

### -param pCurrDM

Caller-supplied pointer to a <a href="/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetdevmodeforpage">GdiGetDevmodeForPage</a>.

## -returns

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.

## -remarks

The <b>GdiResetDCEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

Print processors must call <b>GdiResetDCEMF</b> whenever it is necessary to reset the printer's device context. The function must be called whenever the <a href="/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetdevmodeforpage">GdiGetDevmodeForPage</a> function indicates that the current document page's <a href="/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure is not identical to that of the previous document page.

For additional information, see <a href="/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.
