---
UID: NF:fcb.RxCreateVNetRoot
title: RxCreateVNetRoot function (fcb.h)
description: RxCreateVNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.
old-location: ifsk\rxcreatevnetroot.htm
tech.root: ifsk
ms.assetid: 852cc319-4bcd-427d-802f-3c82c72901f0
ms.date: 04/16/2018
ms.keywords: RxCreateVNetRoot, RxCreateVNetRoot function [Installable File System Drivers], fcb/RxCreateVNetRoot, ifsk.rxcreatevnetroot, rxref_adf9e6de-8b07-488e-86de-0d42036c3d7c.xml
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, Fcb.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxCreateVNetRoot
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCreateVNetRoot function


## -description


<b>RxCreateVNetRoot</b> allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. 


## -parameters




### -param RxContext [in]

A pointer to the RDBSS RX_CONTEXT containing the IRP describing a create operation.


### -param NetRoot [in]

A pointer to the associated NET_ROOT structure.


### -param CanonicalName [in]

A pointer to the canonical name to be inserted in the name table.


### -param LocalNetRootName [in]

A pointer to the local NET_ROOT name without the prefix name.


### -param FilePath [in]

A pointer to a file pathname. This parameter is not currently used and can be <b>NULL</b>.


### -param RxConnectionId [in]

A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the name table.


## -returns



<b>RxCreateVNetRoot</b> returns a pointer to a newly created V_NET_ROOT data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



The <b>RxCreateVNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a V_NET_ROOT needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateVNetRoot</b>, a lock on the name table associated with the device object member of the <i>RxContext</i> parameter must be acquired in exclusive mode. 

<b>RxCreateVNetRoot</b> sets a variety of security context parameters on the V_NET_ROOT structure based on parameters from the RX_CONTEXT. These parameters include the following: <i>LogonId</i>, <i>SessionId</i>, <i>pUserName</i>, <i>pUserDomainName</i>, <i>pPassword</i>, and <i>Flags</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554751">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554376">RxCreateSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554409">RxFinalizeConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554421">RxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554432">RxFinalizeSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554450">RxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554454">RxFinishFcbInitialization</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554463">RxForceFinalizeAllVNetRoots</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554493">RxInferFileType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554728">RxSetSrvCallDomainName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554608">RxpDereferenceNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554627">RxpReferenceNetFcb</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>
 

 

