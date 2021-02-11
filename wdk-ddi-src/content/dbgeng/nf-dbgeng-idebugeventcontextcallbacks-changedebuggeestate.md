---
UID: NF:dbgeng.IDebugEventContextCallbacks.ChangeDebuggeeState
tech.root: 
title: IDebugEventContextCallbacks::ChangeDebuggeeState
ms.date: 02/10/2021
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgeng.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugEventContextCallbacks::ChangeDebuggeeState
f1_keywords:
 - IDebugEventContextCallbacks::ChangeDebuggeeState
 - dbgeng/IDebugEventContextCallbacks::ChangeDebuggeeState
dev_langs:
 - c++
---

## -description


Debuggee state, such as registers or data spaces, has changed.

This is an informational callback notifying the provider about changes in debug state.  The return value of this callbacks is ignored.  Implementations can not call back into the engine.

## -parameters

### -param Flags

### -param Argument

### -param Context

### -param ContextSize

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)