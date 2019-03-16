---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticSymbol
title: IDebugSymbols3::AddSyntheticSymbol (dbgeng.h)
description: The AddSyntheticSymbol method adds a synthetic symbol to a module in the current process.
old-location: debugger\addsyntheticsymbol.htm
tech.root: debugger
ms.assetid: 17fe1fbc-ca55-4d4d-af79-73baad410bfb
ms.date: 05/03/2018
ms.keywords: AddSyntheticSymbol, AddSyntheticSymbol method [Windows Debugging], AddSyntheticSymbol method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AddSyntheticSymbol method, IDebugSymbols3.AddSyntheticSymbol, IDebugSymbols3::AddSyntheticSymbol, IDebugSymbols_8dcf97a7-eb9c-44aa-a2a7-1ad74cb396c1.xml, dbgeng/IDebugSymbols3::AddSyntheticSymbol, debugger.addsyntheticsymbol
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dbgeng.h
api_name:
- IDebugSymbols3.AddSyntheticSymbol
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AddSyntheticSymbol


## -description


The <b>AddSyntheticSymbol</b>  method adds a synthetic symbol to a module in the <a href="https://msdn.microsoft.com/295b05a3-e27f-4761-a562-7e87e25bfd3b">current process</a>.


## -parameters




### -param Offset [in]

Specifies the location in the process's virtual address space of the synthetic symbol.


### -param Size [in]

Specifies the size in bytes of the synthetic symbol.


### -param Name [in]

Specifies the name of the synthetic symbol.


### -param Flags [in]

Set to DEBUG_ADDSYNTHSYM_DEFAULT.


### -param Id [out, optional]

Receives the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure that identifies the synthetic symbol.  If <i>Id</i> is <b>NULL</b>, this information is not returned.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The location of the synthetic symbol must not be the same as the location of another symbol.

If the module containing a synthetic symbol is reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see <a href="https://msdn.microsoft.com/1de1441f-b4d7-49e9-87ad-392a75b3d4be">Synthetic Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>
 

 

