---
UID: NF:wiamindr_lh.IWiaDrvItem.UnlinkItemTree
title: IWiaDrvItem::UnlinkItemTree
description: The IWiaDrvItem::UnlinkItemTree method unlinks the driver item tree and releases all items in the tree.
old-location: image\iwiadrvitem_unlinkitemtree.htm
tech.root: image
ms.assetid: f6fb2929-177b-44cd-a313-8620ba9b2907
ms.date: 05/03/2018
ms.keywords: DrvItem_70e5eaf0-4115-4207-9ea2-53ca8c210795.xml, IWiaDrvItem interface [Imaging Devices],UnlinkItemTree method, IWiaDrvItem.UnlinkItemTree, IWiaDrvItem::UnlinkItemTree, UnlinkItemTree, UnlinkItemTree method [Imaging Devices], UnlinkItemTree method [Imaging Devices],IWiaDrvItem interface, image.iwiadrvitem_unlinkitemtree, wiamindr_lh/IWiaDrvItem::UnlinkItemTree
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	wiamindr_lh.h
api_name:
-	IWiaDrvItem.UnlinkItemTree
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::UnlinkItemTree


## -description


The <b>IWiaDrvItem::UnlinkItemTree</b> method unlinks the driver item tree and releases all items in the tree.


## -parameters




### -param __MIDL__IWiaDrvItem0005






#### - lFlags [in]

Indicates how the driver item tree should be unlinked. This parameter must be set to one of the following values. See the Microsoft Windows SDK documentation for a description of the WIA item type flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WiaItemTypeDeleted

</td>
<td>
The item is marked as deleted from the tree.

</td>
</tr>
<tr>
<td>
WiaItemTypeDisconnected

</td>
<td>
The item represents a disconnected device.

</td>
</tr>
</table>
 


## -returns



If the method succeeds, it returns S_OK. If the method is called on a nonroot item, it returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.




## -remarks



Minidrivers must call this method on the root item in the driver item tree when they want to invalidate the tree. This is typically done when the driver is being unloaded or when the minidriver needs to rebuild the driver item tree.



