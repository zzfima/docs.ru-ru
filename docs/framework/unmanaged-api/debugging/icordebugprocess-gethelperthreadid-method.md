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
ms.workload: dotnet
ms.openlocfilehash: 03e801cb58b8f5c3f658085fcee4288278e545c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="69dd2-102">Метод ICorDebugProcess::GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="69dd2-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="69dd2-103">Получает идентификатор потока операционной системы (ОС) вспомогательный внутренний поток отладчика.</span><span class="sxs-lookup"><span data-stu-id="69dd2-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69dd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69dd2-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69dd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69dd2-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="69dd2-106">[out] Указатель на ОС потока идентификатор вспомогательный внутренний поток отладчика.</span><span class="sxs-lookup"><span data-stu-id="69dd2-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69dd2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="69dd2-107">Remarks</span></span>  
 <span data-ttu-id="69dd2-108">При отладке управляемого и неуправляемого кода это отладчик обязан гарантировать непрерывное потока с указанным Идентификатором, если он попадает на точку останова размещенную отладчиком.</span><span class="sxs-lookup"><span data-stu-id="69dd2-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="69dd2-109">Отладчик может возникнуть необходимость скрыть этот поток от пользователя.</span><span class="sxs-lookup"><span data-stu-id="69dd2-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="69dd2-110">Если ни один вспомогательный поток существует в процессе, `GetHelperThreadID` метод возвращает нуль в *`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="69dd2-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in *`pThreadID`.</span></span>  
  
 <span data-ttu-id="69dd2-111">Идентификатор потока вспомогательного потока кэшировать нельзя, поскольку со временем может меняться.</span><span class="sxs-lookup"><span data-stu-id="69dd2-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="69dd2-112">Необходимо повторно запросить идентификатор потока при каждом событии остановки.</span><span class="sxs-lookup"><span data-stu-id="69dd2-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="69dd2-113">Идентификатор потока вспомогательный поток отладчика будут правильными для каждой неуправляемой [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) события, позволяя тем самым отладчику определить ИД вспомогательного потока и скрыть его от пользователя.</span><span class="sxs-lookup"><span data-stu-id="69dd2-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="69dd2-114">Поток, который указан в качестве вспомогательного потока во время неуправляемый `ICorDebugManagedCallback::CreateThread` событие никогда не будет выполняться управляемого пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="69dd2-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69dd2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="69dd2-115">Requirements</span></span>  
 <span data-ttu-id="69dd2-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69dd2-117">**Заголовок:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="69dd2-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="69dd2-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69dd2-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="69dd2-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69dd2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69dd2-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69dd2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
