---
title: Метод ICorDebugMDA::GetOSThreadId
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d676e0fad33ca994b2e5bcd7adf269e306cb55
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761919"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="22f0f-102">Метод ICorDebugMDA::GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="22f0f-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="22f0f-103">Получает идентификатор потока операционной системы (ОС), на котором помощник по отладке управляемого (кода MDA), представленного [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) выполняется.</span><span class="sxs-lookup"><span data-stu-id="22f0f-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22f0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22f0f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22f0f-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="22f0f-106">[out] Указатель на идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="22f0f-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22f0f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="22f0f-107">Remarks</span></span>  
 <span data-ttu-id="22f0f-108">Поток операционной системы используется вместо ICorDebugThread, чтобы допускать ситуации, в которых MDA вызывается в собственном потоке или в управляемом потоке, который еще не вошел в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="22f0f-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f0f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="22f0f-109">Requirements</span></span>  
 <span data-ttu-id="22f0f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22f0f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f0f-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22f0f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22f0f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22f0f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22f0f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f0f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f0f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="22f0f-114">See also</span></span>

- [<span data-ttu-id="22f0f-115">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="22f0f-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="22f0f-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="22f0f-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
