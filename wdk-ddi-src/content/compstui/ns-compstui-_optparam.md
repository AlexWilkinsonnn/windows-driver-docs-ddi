---
UID: NS:compstui._OPTPARAM
title: _OPTPARAM (compstui.h)
description: An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a property sheet option. The array's address is included in an OPTTYPE structure.
old-location: print\optparam.htm
tech.root: print
ms.assetid: d0cd2867-783c-4a41-a819-e919d4ffc1e3
ms.date: 04/20/2018
ms.keywords: "*POPTPARAM, OPTPARAM, OPTPARAM structure [Print Devices], POPTPARAM, POPTPARAM structure pointer [Print Devices], _OPTPARAM, compstui/OPTPARAM, compstui/POPTPARAM, cpsuifnc_1c22c283-993e-45d7-b0c7-1148eafeb13c.xml, print.optparam"
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
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
- HeaderDef
api_location:
- compstui.h
api_name:
- OPTPARAM
product:
- Windows
targetos: Windows
req.typenames: OPTPARAM, *POPTPARAM
---

# _OPTPARAM structure


## -description


An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a <a href="https://msdn.microsoft.com/572330d6-1a1b-46fd-bfb4-be2b0990bca4">property sheet option</a>. The array's address is included in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559670">OPTTYPE</a> structure.


## -struct-fields




### -field cbSize

Size, in bytes, of the OPTPARAM structure.


### -field Flags

Optional bit flags that modify the parameter's characteristics. The following flags can be set in any combination:





#### OPTPF_DISABLED

If set, the parameter is not user-selectable. Can be used with the following option types:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562825">TVOT_2STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562827">TVOT_3STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562833">TVOT_COMBOBOX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562839">TVOT_LISTBOX</a>






#### OPTPF_HIDE

If set, the parameter not displayed in the treeview. Can be used with the following option types:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562827">TVOT_3STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562833">TVOT_COMBOBOX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562839">TVOT_LISTBOX</a>






#### OPTPF_ICONID_AS_HICON

If set, the <b>IconID</b> member contains an icon handle.

If not set, the <b>IconID</b> member contains an icon resource identifier.





#### OPTPF_OVERLAY_NO_ICON

If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the <b>IconID</b> member.





#### OPTPF_OVERLAY_STOP_ICON

If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the <b>IconID</b> member.





#### OPTPF_OVERLAY_WARNING_ICON

If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the <b>IconID</b> member.





#### OPTPF_USE_HDLGTEMPLATE

If set, <b>lParam</b> contains a template handle.

If not set, <b>lParam</b> contains a template resource identifier.

(Used only if <b>Style</b> is PUSHBUTTON_TYPE_DLGPROC.)


### -field Style

Push button style, used only for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562844">TVOT_PUSHBUTTON</a> option type.


### -field pData

Pointer to the parameter's value. Use of this member is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.


### -field IconID

Usually identifies the icon to be associated with the option parameter, but is sometimes used for other purposes. Use of this member is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.


### -field lParam

Use of this member is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.


### -field dwReserved

Reserved, must be initialized to zero.


## -remarks



If the OPTPF_HIDE flag is set in all the OPTPARAM structures associated with an option, CPSUI hides the entire option.



