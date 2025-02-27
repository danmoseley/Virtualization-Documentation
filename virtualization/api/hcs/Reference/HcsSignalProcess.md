---
title: HcsSignalProcess
description: HcsSignalProcess
author: sethmanheim
ms.author: roharwoo
ms.topic: reference
ms.service: virtualization
ms.date: 06/09/2021
api_name:
- HcsSignalProcess
api_location:
- computecore.dll
api_type:
- DllExport
topic_type: 
- apiref
---
# HcsSignalProcess

## Description

Sends a signal to a process in a compute system.

## Syntax

```cpp
HRESULT WINAPI
HcsSignalProcess(
    _In_ HCS_PROCESS process,
    _In_ HCS_OPERATION operation,
    _In_opt_ PCWSTR options
    );
```

## Parameters

`process`

The handle to the process to send the signal to.

`operation`

The handle to the operation that tracks the signal.

`options`

Optional JSON document of [SignalProcessOptions](./../SchemaReference.md#SignalProcessOptions) specifying the detailed signal.

## Return Values

The function returns [HRESULT](./HCSHResult.md).

If the return value is `S_OK`, it means the operation started successfully. Callers are expected to get the operation's result using [`HcsWaitForOperationResultAndProcessInfo`](./HcsWaitForOperationResultAndProcessInfo.md) or [`HcsGetOperationResultAndProcessInfo`](./HcsGetOperationResultAndProcessInfo.md).


## Operation Results

The return value of [`HcsWaitForOperationResultAndProcessInfo`](./HcsWaitForOperationResultAndProcessInfo.md) or [`HcsGetOperationResultAndProcessInfo`](./HcsGetOperationResultAndProcessInfo.md) based on current operation listed as below.

| Operation Result Value | Description |
| -- | -- |
| `S_OK` | The signal was sent to the process successfully |

## Requirements

|Parameter|Description|
|---|---|
| **Minimum supported client** | Windows 10, version 1809 |
| **Minimum supported server** | Windows Server 2019 |
| **Target Platform** | Windows |
| **Header** | ComputeCore.h |
| **Library** | ComputeCore.lib |
| **Dll** | ComputeCore.dll |
