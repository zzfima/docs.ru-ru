---
title: "Метод ICorDebugProcess::GetHelperThreadID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 092e99cb1d5534cee56db08b5a2eedaaa2fc4724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="a5c01-102">Метод ICorDebugProcess::GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="a5c01-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="a5c01-103">Получает идентификатор потока операционной системы (ОС) вспомогательный внутренний поток отладчика.</span><span class="sxs-lookup"><span data-stu-id="a5c01-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5c01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5c01-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5c01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5c01-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="a5c01-106">[out] Указатель на ОС потока идентификатор вспомогательный внутренний поток отладчика.</span><span class="sxs-lookup"><span data-stu-id="a5c01-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5c01-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5c01-107">Remarks</span></span>  
 <span data-ttu-id="a5c01-108">При отладке управляемого и неуправляемого кода это отладчик обязан гарантировать непрерывное потока с указанным Идентификатором, если он попадает на точку останова размещенную отладчиком.</span><span class="sxs-lookup"><span data-stu-id="a5c01-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="a5c01-109">Отладчик может возникнуть необходимость скрыть этот поток от пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5c01-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="a5c01-110">Если ни один вспомогательный поток существует в процессе, `GetHelperThreadID` метод возвращает нуль в *`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="a5c01-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in *`pThreadID`.</span></span>  
  
 <span data-ttu-id="a5c01-111">Идентификатор потока вспомогательного потока кэшировать нельзя, поскольку со временем может меняться.</span><span class="sxs-lookup"><span data-stu-id="a5c01-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="a5c01-112">Необходимо повторно запросить идентификатор потока при каждом событии остановки.</span><span class="sxs-lookup"><span data-stu-id="a5c01-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="a5c01-113">Идентификатор потока вспомогательный поток отладчика будут правильными для каждой неуправляемой [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) события, позволяя тем самым отладчику определить ИД вспомогательного потока и скрыть его от пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5c01-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="a5c01-114">Поток, который указан в качестве вспомогательного потока во время неуправляемый `ICorDebugManagedCallback::CreateThread` событие никогда не будет выполняться управляемого пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="a5c01-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5c01-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a5c01-115">Requirements</span></span>  
 <span data-ttu-id="a5c01-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5c01-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5c01-117">**Заголовок:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="a5c01-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="a5c01-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5c01-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="a5c01-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5c01-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5c01-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5c01-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
