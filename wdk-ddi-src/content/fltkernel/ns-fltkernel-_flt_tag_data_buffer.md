---
UID: NS:fltkernel._FLT_TAG_DATA_BUFFER
title: _FLT_TAG_DATA_BUFFER (fltkernel.h)
description: The FLT_TAG_DATA_BUFFER structure contains information about a reparse point tag.
old-location: ifsk\flt_tag_data_buffer.htm
tech.root: ifsk
ms.assetid: a101e0c8-7121-42b6-aa0e-299f37af8e47
ms.date: 04/16/2018
ms.keywords: "*PFLT_TAG_DATA_BUFFER, FLT_TAG_DATA_BUFFER, FLT_TAG_DATA_BUFFER structure [Installable File System Drivers], FltSystemStructures_47092b0b-5a4b-40eb-8b5f-f0a182d5e509.xml, PFLT_TAG_DATA_BUFFER, PFLT_TAG_DATA_BUFFER structure pointer [Installable File System Drivers], _FLT_TAG_DATA_BUFFER, fltkernel/FLT_TAG_DATA_BUFFER, fltkernel/PFLT_TAG_DATA_BUFFER, ifsk.flt_tag_data_buffer"
ms.topic: struct
req.header: fltkernel.h
req.include-header: FltKernel.h
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
-	fltkernel.h
api_name:
-	FLT_TAG_DATA_BUFFER
product:
- Windows
targetos: Windows
req.typenames: FLT_TAG_DATA_BUFFER, *PFLT_TAG_DATA_BUFFER
---

# _FLT_TAG_DATA_BUFFER structure


## -description


The FLT_TAG_DATA_BUFFER structure contains information about a reparse point tag. 


## -struct-fields




### -field FileTag

Reparse point tag. 


### -field TagDataLength

Size, in bytes, of the reparse data pointed to by the <b>DataBuffer</b> member.


### -field UnparsedNameLength

Length, in bytes, of the unparsed portion of the file name pointed to by the <b>FileName</b> member of the associated file object.  For more information about the <b>FileName</b> member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>.


### -field SymbolicLinkReparseBuffer

 


### -field SymbolicLinkReparseBuffer.SubstituteNameOffset

 


### -field SymbolicLinkReparseBuffer.SubstituteNameLength

 


### -field SymbolicLinkReparseBuffer.PrintNameOffset

 


### -field SymbolicLinkReparseBuffer.PrintNameLength

 


### -field SymbolicLinkReparseBuffer.Flags

 


### -field SymbolicLinkReparseBuffer.PathBuffer

 


### -field MountPointReparseBuffer

 


### -field MountPointReparseBuffer.SubstituteNameOffset

 


### -field MountPointReparseBuffer.SubstituteNameLength

 


### -field MountPointReparseBuffer.PrintNameOffset

 


### -field MountPointReparseBuffer.PrintNameLength

 


### -field MountPointReparseBuffer.PathBuffer

 


### -field GenericReparseBuffer

 


### -field GenericReparseBuffer.DataBuffer

 


### -field GenericGUIDReparseBuffer

 


### -field GenericGUIDReparseBuffer.TagGuid

 


### -field GenericGUIDReparseBuffer.DataBuffer

 




#### - ( unnamed union )

 



#### SymbolicLinkReparseBuffer



##### SubstituteNameOffset

Offset, in bytes, of the substitute name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof(</b>WCHAR<b>)</b> to get the array index. 



##### SubstituteNameLength

Length, in bytes, of the substitute name string. If the substitute name string is NULL-terminated, <b>SubstituteNameLength</b> does not include space for the UNICODE_NULL terminator. 



##### PrintNameOffset

Offset, in bytes, of the print name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof(</b>WCHAR<b>)</b> to get the array index. 



##### PrintNameLength

Length, in bytes, of the print name string. If the print name string is NULL-terminated, <b>PrintNameLength</b> does not include space for the UNICODE_NULL terminator. 



##### Flags

If the SYMLINK_FLAG_RELATIVE flag is set, the <b>PathBuffer</b> path is relative to the path contained in the <b>FileName</b> member of the associated file object.



##### PathBuffer

First character of the path string. This character is followed in memory by the remainder of the string. 



#### MountPointReparseBuffer



##### SubstituteNameOffset

Offset, in bytes, of the substitute name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof(</b>WCHAR<b>)</b> to get the array index. 



##### SubstituteNameLength

Length, in bytes, of the substitute name string. If the substitute name string is NULL-terminated, <b>SubstituteNameLength</b> does not include space for the UNICODE_NULL terminator. 



##### PrintNameOffset

Offset, in bytes, of the print name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof(</b>WCHAR<b>)</b> to get the array index. 



##### PrintNameLength

Length, in bytes, of the print name string. If the print name string is NULL-terminated, <b>PrintNameLength</b> does not include space for the UNICODE_NULL terminator. 



##### PathBuffer

First character of the path string. This character is followed in memory by the remainder of the string. 



#### GenericReparseBuffer



##### DataBuffer

Pointer to a buffer that contains user-defined data for the reparse point. 



#### GenericGUIDReparseBuffer



##### TagGuid

Globally unique identifier (GUID) that uniquely identifies the type of reparse point. If <b>FileTag</b> is not a Microsoft tag, this member cannot be <b>NULL</b>. 



##### DataBuffer

Pointer to a buffer that contains user-defined data for the reparse point. 


## -remarks



A minifilter can use the FLT_TAG_DATA_BUFFER structure to store information about a reparse point tag. 

A pointer to an FLT_TAG_DATA_BUFFER structure that contains reparse point tag data for an operation is stored in the <b>TagData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure for the operation. 

The FLT_TAG_DATA_BUFFER_HEADER_SIZE macro returns the size of the fixed portion of the FLT_TAG_DATA_BUFFER structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>
 

 

