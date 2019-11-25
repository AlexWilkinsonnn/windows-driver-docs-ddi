---
UID: NN:xpsrassvc.IXpsRasterizationFactory
title: IXpsRasterizationFactory (xpsrassvc.h)
description: The IXpsRasterizationFactory interface represents an object factory for creating XPS rasterizer objects.
old-location: print\ixpsrasterizationfactory_interface.htm
tech.root: print
ms.assetid: 559bdc65-282e-42b2-998a-276202376c1e
ms.date: 04/20/2018
ms.keywords: IXpsRasterizationFactory, IXpsRasterizationFactory interface [Print Devices], IXpsRasterizationFactory interface [Print Devices],described, print.ixpsrasterizationfactory_interface, print_xpsrast_50eb7bf8-2753-47e1-b63b-81639ac26bb7.xml, xpsrassvc/IXpsRasterizationFactory
ms.topic: interface
f1_keywords:
 - "xpsrassvc/IXpsRasterizationFactory"
req.header: xpsrassvc.h
req.include-header: 
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- xpsrassvc.h
api_name:
- IXpsRasterizationFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizationFactory interface


## -description


The <b>IXpsRasterizationFactory</b> interface represents an object factory for creating XPS rasterizer objects. Rasterizer objects created by the factory implement <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizer">IXpsRasterizer</a> interfaces. An XPSDrv filter uses a rasterizer object to convert an XPS fixed page to one or more bitmap images.

An XPSDrv filter obtains a reference to an <b>IXpsRasterizationFactory</b> interface instance from the property bag received from the print filter pipeline manager. The pipeline manager calls the filter's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-initializefilter">IPrintPipelineFilter::InitializeFilter</a> method and passes in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinepropertybag">IPrintPipelinePropertyBag</a> pointer. The interface reference is a VT_UNKNOWN property value that is identified by the property name <b>MS_IXpsRasterizationFactory</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsRasterizationFactory</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IXpsRasterizationFactory</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

