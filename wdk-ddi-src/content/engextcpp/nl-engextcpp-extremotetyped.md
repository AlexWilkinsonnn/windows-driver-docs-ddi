---
UID: NL:engextcpp.ExtRemoteTyped
title: ExtRemoteTyped
author: windows-driver-content
description: The ExtRemoteTyped class provides the ability to manipulate typed data on the target.
old-location: debugger\extremotetyped.htm
tech.root: debugger
ms.assetid: 1f5d71a5-fa60-4819-9838-2b035ef21374
ms.date: 08/09/2018
ms.keywords: EngExtCpp_Ref_04970dac-e759-4a04-a1e0-8dab752c1418.xml, ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging], ExtRemoteTyped class [Windows Debugging],described, debugger.extremotetyped, engextcpp/ExtRemoteTyped
ms.topic: class
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped class


## -description


The <b>ExtRemoteTyped</b> class provides the ability to manipulate typed data on the target.  An instance of this class represents a small region of memory on the target. This region is interpreted as a specific type.  This class provides methods for manipulating the memory according to the type and for accessing the object hierarchy on the target.

<b>ExtRemoteTyped</b> is a subclass of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>.

The <b>ExtRemoteTyped</b> class includes the following constructors, operators, and methods:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544349">operator=</a>


</dd>

<dd>

<a href="https://msdn.microsoft.com/bfeafa09-49b7-45b3-84d8-afad5f43b78e">Copy(Debug Typed Data)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/7cc91411-3332-4a33-8873-832f71fd3281">Copy(ExtRemoteTyped)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">Set(bool)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">Set(pcstr)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">Set(pcstr ulong64)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">Set(pcstr ulong64 bool)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/ae478779-8ec1-4a50-a37c-3017aca2c912">SetPrint</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/c206d8e7-1a90-4866-868b-20275a52e2dd">HasField</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a>


</dd>
<dd>
<b>GetFieldSize</b>

</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/be662551-c4d3-4979-8a9b-c913fb6bd336">Field</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/abe43441-3e00-4d85-ae84-dd738303ab1b">ArrayElement</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/27a90926-95f4-43cd-b8d1-1b60ad23d737">Dereference</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/1f237e8a-c0d3-4812-a96d-4cdc6f8e31df">GetPointerTo</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439396">Eval</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8">operator*</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544338">operator[]</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544338">operator[]</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544338">operator[]</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544338">operator[]</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549408">GetTypeName</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/fda88a3d-4cdf-4be1-87a7-29e312453686">OutTypeName</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/e9c11c07-bd4a-4d49-a820-4617be691c80">OutSimpleValue</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/8f5b3e8b-1b01-4a14-b472-cb5de82e869a">OutFullValue</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f7d24a3b-b5a8-4924-85d9-8bf7983b95fa">OutTypeDefinition</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/041f585a-bc1f-4413-9d68-ae18969e4d75">Release</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/5f966bf0-2dc3-4422-bfec-09d1b136f9f0">GetTypeFieldOffset</a>


</dd>
</dl><pre class="syntax" xml:space="preserve"><code>class ExtRemoteTyped : public ExtRemoteData
{
public:
    DEBUG_TYPED_DATA  m_Typed;
    bool  m_Release;
};


</code></pre>
<dl>
<dt><a id="m_Typed"></a><a id="m_typed"></a><a id="M_TYPED"></a><b>m_Typed</b></dt>
<dd>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff541706">DEBUG_TYPED_DATA</a> structure that describes the typed data represented by this instance of <b>ExtRemoteTyped</b>.

</dd>
<dt><a id="m_Release"></a><a id="m_release"></a><a id="M_RELEASE"></a><b>m_Release</b></dt>
<dd>
Indicates whether or not the destructor for this instance of <b>ExtRemoteTyped</b> needs to release the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541706">DEBUG_TYPED_DATA</a> structure that is specified in <b>m_Typed</b>.

</dd>
</dl>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541706">DEBUG_TYPED_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>
 

 

