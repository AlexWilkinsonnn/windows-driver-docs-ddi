---
UID: NS:printoem._PSCRIPT5_PRIVATE_DEVMODE
title: "_PSCRIPT5_PRIVATE_DEVMODE" (printoem.h)
description: The PSCRIPT5_PRIVATE_DEVMODE structure enables Pscript5 plug-ins to determine the size of the private portion of Pscript5's DEVMODEW structure.
old-location: print\pscript5_private_devmode.htm
tech.root: print
ms.assetid: e2ae002b-2bc9-4e5e-b9b6-bb76849c2cba
ms.date: 04/20/2018
ms.keywords: "*PPSCRIPT5_PRIVATE_DEVMODE, PPSCRIPT5_PRIVATE_DEVMODE, PPSCRIPT5_PRIVATE_DEVMODE structure pointer [Print Devices], PSCRIPT5_PRIVATE_DEVMODE, PSCRIPT5_PRIVATE_DEVMODE structure [Print Devices], _PSCRIPT5_PRIVATE_DEVMODE, print.pscript5_private_devmode, print_unidrv-pscript_ui_4dd76ed6-3e60-43dd-a50b-05561574602a.xml, printoem/PPSCRIPT5_PRIVATE_DEVMODE, printoem/PSCRIPT5_PRIVATE_DEVMODE"
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
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
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	PSCRIPT5_PRIVATE_DEVMODE
product:
- Windows
targetos: Windows
req.typenames: PSCRIPT5_PRIVATE_DEVMODE, *PPSCRIPT5_PRIVATE_DEVMODE
---

# _PSCRIPT5_PRIVATE_DEVMODE structure


## -description


The PSCRIPT5_PRIVATE_DEVMODE structure enables Pscript5 plug-ins to determine the size of the private portion of Pscript5's DEVMODEW structure.


## -struct-fields




### -field wReserved

Reserved for system use.


### -field wSize

The size, in bytes, of the private portion of Pscript5's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


## -remarks



This structure and associated macro are available in Windows 2000 and later. For information about the public and private sections of the DEVMODEW structure, see <a href="https://msdn.microsoft.com/26212e3b-a591-4ed6-b441-b130d8d4d948">The DEVMODEW Structure</a>. 

Printoem.h defines a macro that you can use to determine the size of the private portion of Pscript5's DEVMODEW structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE(pdm)\
( ( (pdm)-&gt;dmDriverExtra &gt; (FIELD_OFFSET(PSCRIPT5_PRIVATE_DEVMODE, wSize) + sizeof(WORD)) ) ? \
((PPSCRIPT5_PRIVATE_DEVMODE)((PBYTE)(pdm) + (pdm)-&gt; dmSize)) -&gt; wSize : 0 )</pre>
</td>
</tr>
</table></span></div>
The <i>pdm</i> argument in the <b>GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE</b> macro is a pointer to a DEVMODEW structure. The macro determines whether the value of the <b>dmDriverExtra</b> member of the DEVMODEW structure is larger than the byte offset of the <b>wSize</b> member of the PSCRIPT5_PRIVATE_DEVMODE structure. If so, the macro returns the value of the <b>wSize</b> member in the PSCRIPT5_PRIVATE_DEVMODE structure. If not, the macro returns zero.

To safely determine the address of the private portion of your plug-in's DEVMODEW structure, do the following:

<ol>
<li>
Call the <b>GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE</b> macro, passing the address of the DEVMODEW structure in the call.

</li>
<li>
Verify that (pdm)-&gt;dmDriverExtra is larger than the value returned by the macro. (The macro returns the value of the <b>wSize</b> member of the PSCRIPT5_PRIVATE_DEVMODE structure.)

</li>
<li>Determine the address of the private portion of your plug-in's DEVMODEW structure as follows.<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>pdmPlugin = (PBYTE)(pdm) + (pdm)-&gt;dmSize + wSize;</pre>
</td>
</tr>
</table></span></div>
The preceding example starts with the address of the public DEVMODEW structure (<i>pdm</i>), adds the number of bytes of this structure (<i>pdm-</i>&gt;<b>dmSize</b>), and then adds the size in bytes of the Pscript5 private DEVMODEW structure (<b>wSize</b>). A plug-in's private DEVMODEW data begins at this memory address. If there are multiple plug-ins chained together, the address returned by this example is that of the first plug-in's private DEVMODEW data. The second plug-in's private DEVMODEW data follows the first plug-in's private DEVMODEW data, the third plug-in's private DEVMODEW data follows that of the second plug-in's private DEVMODEW data, and so on. A plug-in developer who needs to determine the address of the <i>n</i>-th plug-in's private DEVMODEW data must know the sizes of the private DEVMODEW data for the first <i>n</i> - 1 plug-ins.

</li>
<li>
Verify that the private portion of your plug-in's DEVMODEW structure begins with a valid <a href="https://msdn.microsoft.com/library/windows/hardware/ff559588">OEM_DMEXTRAHEADER</a> structure.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563565">UNIDRV_PRIVATE_DEVMODE</a>
 

 

